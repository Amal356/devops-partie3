# Activité 4 - Infrastructure automatisée avec Vagrant et Ansible (Étapes 43 à 45)

## Étape 43 : Playbook Ansible de déploiement
**Objectif :** Créer un playbook permettant de déployer automatiquement le DevSecOps Portfolio avec Docker Compose sur une VM.

Le playbook `deploy.yml` installe les prérequis (Git, Docker), clone le dépôt GitHub et lance le portfolio avec Docker Compose.
**Commande utilisée :** 
`ansible-playbook -i inventory.ini deploy.yml`

**Captures :**
* Le `PLAY RECAP` montrant le succès de l'exécution (failed=0) :
![Résultat Ansible](../captures-activite4/etape43-ansible.png)
* Le Portfolio accessible sur le port 8081 :
![Portfolio déployé](../captures-activite4/etape43-portfolio.png)

---

## Étape 44 : Automatisation complète avec Vagrant
**Objectif :** Modifier le projet Vagrant pour lancer automatiquement le playbook Ansible après la création de la VM.
L'objectif est d'obtenir la chaîne : `vagrant up` -> création VM -> configuration Ansible -> installation Docker -> déploiement Portfolio.

Le fichier `Vagrantfile` a été modifié pour inclure le provisionneur `ansible_local` sur la machine `docker-vm`.
```ruby
dvm.vm.provision "ansible_local" do |ansible|
  ansible.playbook = "activite4/deploy.yml"
  ansible.raw_arguments = ["--connection=local"]
end
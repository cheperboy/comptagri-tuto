# 1. deploiement
## 1.1 useful commands

creer la base, executer seeds.rb
	rake db:reset --trace

## 1.2 créer saison

### 1.2.1 préparation des données

creer les donnees de la saison:
google spreadsheet : editer fichier assollement avec generation code ruby
copier/coller colonne générée (ruby) dans fichier

	db/datas/saison_201X.rb

executer macros textmate 
pour supprimer les "DELETE_BEFORE" et "DELETE_AFTER"

	Bundless/COMPTAGRI/replace_DELETE_BEFORE_AFTER

pour remplacer les virgules des nombres flottants excel par des points
selectionner uniquement le code généré 

	Bundless/COMPTAGRI/replace_comma_by_point


### 1.2.2 préparation du script
Editer le rakefile pour modifier le script de la saison précédante

	task :create_saison_201[X-1] => :environment do 

modifier le nom de la fonction et appeler le bon fichier saison_201[X].rb

	task :create_saison_201[X] => :environment do 
	file = File.join(Rails.root, 'db', 'datas', 'saison_201[X].rb')

### 1.2.3 Exécution 

## 1.3 supprimer saison
une commande existe dans le rake file pour supprimer une saison et ses parcelles.
Attention, a utiliser avec précaution en production!
mettre a jour le script avant utilisation.

	task :delete_saison_2013
	



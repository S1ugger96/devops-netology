# devops-netology

GITLAB



## .gitignore
Файл terraform/.gitignore игнорирует файлы по следующим правилам:
- **/.terraform/* - все файлы внутри любой папки .terraform, на любом уровне вложенности
- *.tfstate - любой файл, имя которого заканчивается на .tfstate
- *.tfstate.* - любой файл, в имени которого после .tfstate идёт точка и что угодно дальше
- crash.log - файл с именем ровно crash.log
- crash.*.log - файл, начинающийся с crash., затем любые символы, и заканчивающийся на .log
- *.tfvars - любой файл, заканчивающийся на .tfvars
- *.tfvars.json - любой файл, заканчивающийся на .tfvars.json
- override.tf - файл с именем ровно override.tf
- override.tf.json - файл с именем ровно override.tf.json
- *_override.tf - любой файл, заканчивающийся на _override.tf
- *_override.tf.json - любой файл, заканчивающийся на _override.tf.json
- *tfplan* - любой файл, в имени которого есть буквосочетание tfplan
- .terraformrc - файл с именем ровно .terraformrc
- terraform.rc - файл с именем ровно terraform.rc

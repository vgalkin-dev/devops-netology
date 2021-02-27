# Все игноры пока касаются только содержимого каталога Terraform


Подкаталоги .terraform; .terraformrc
# Terraform/.terraform/

Всё что:
* оканчивается .tfstate; .tfvars; _override.tf; _override.tf.json
* имеет вхождение .tfstate. в названии
#*.tfstate
#*.tfstate.*
#*.tfvars
#*_override.tf
#*_override.tf.json


Конкретный файл
#crash.log
#override.tf
#override.tf.json
#terraform.rc

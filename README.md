# devops-netology
Будут проигнорированы:
**/.terraform/*
поддиректория .terraform и все все директории и файлы ниже

*.tfstate
*.tfstate.*
все файлы с расширением .tfstate и файлы содержащие .tfstate.

crash.log
crash.*.log
все файлы crash.log и файлы начинающиеся с crash. и расширением .log

*.tfvars
*.tfvars.json
все файлы с расширением .tfvars и заканчивающиеся на .tfvars.json

override.tf
override.tf.json
*_override.tf
*_override.tf.json

все файлы override.tf, override.tf.json, все файлы вида aaa_override.tf и
bbb_override.tf.json

.terraformrc
terraform.rc
Будут проигнорированы все файлы terraform.rc и заканчивающиеся на .terraformrc

# !example_override.tf
Закоментировано, но если бы нет, то не будет игнорироваться, если бы был
соответствующий шаблон на игнорирование.

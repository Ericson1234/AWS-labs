## Amazon EFS
sudo yum -y update
mkdir ~/efs-mount-point 

# Instalar utilidades de EFS
sudo yum install -y amazon-efs-utils

# Montar utilizando el Mount Helper
sudo mount -t efs -o tls fs-0e573817e9f896a2a.efs.us-east-1.amazonaws.com:/ ~/efs-mount-point

# Desmontar el sistema de archivos EFS
sudo umount ~/efs-mount-point
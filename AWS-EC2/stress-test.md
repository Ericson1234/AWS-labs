# Habilitar el repositorio:
sudo dnf install -y stress-ng

# Instalar las utilidades stress
sudo yum install stress -y

# Ejecutar la utilidad de estrés con x número de trabajadores de la CPU
sudo stress --cpu 5
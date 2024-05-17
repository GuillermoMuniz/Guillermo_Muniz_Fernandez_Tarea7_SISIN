Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.50.55"
  # Sincronizamos la carpeta del host a la maquina virtual
  config.vm.synced_folder ".", "/vagrant-tarea7"


  config.vm.provision "shell", inline: <<-SHELL

      # Instalación de los binarios de PHP, el driver mysqli y la extensión FPM para realizar peticiones de tipo RESTful
       sudo apt install -y nginx
       sudo apt-get update
       sudo apt-get install -y php php-mysqli
       # Tratar la petición desde el Front al Back: API de tipo RESTful
       sudo apt-get install php7.0-fpm

      # Generar archivo SQL con los registros de los diferentes Módulos Profesionales
    echo "-- Insertar datos de ejemplo en la tabla 'horarioModulos'" > /home/vagrant/gestion_horarios.sql
    echo "INSERT INTO gestion_horarios.horarioModulos (nombre, apellido, asignatura, anioIngreso) VALUES" >> /home/vagrant/gestion_horarios.sql
    echo "('Diego', 'Alonso', 'SISIN', 2022)," >> /home/vagrant/gestion_horarios.sql
    echo "('Diego', 'Mateos', 'PROG', 2022)," >> /home/vagrant/gestion_horarios.sql
    echo "('Guillermo', 'Roman', 'ENDES', 2022)," >> /home/vagrant/gestion_horarios.sql
    echo "('Beatriz', 'Lopez', 'LMGSI', 2020)," >> /home/vagrant/gestion_horarios.sql
    echo "('Lorena', 'Franco', 'LEUP', 2021)," >> /home/vagrant/gestion_horarios.sql
    echo "('Tomas', 'Huerta', 'BADAT', 2020)" >> /home/vagrant/gestion_horarios.sql
   
    

  SHELL

end

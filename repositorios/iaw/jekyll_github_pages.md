## Instalacion del tema minima desde Github 
**1- Preparamos la maquina virtual debian configurando la tarjeta de red .**  
Configuración IPv4: /etc/network/interfaces 
auto lo  
iface lo inet loopback  
#Configuración IPv4  
auto enp0s3  
#allow-hotplug enp0s3  
iface enp0s3 inet static  
#iface enp0s3 inet dhcp  
address 10.0.16.2XX  
netmask 255.255.255.0  
gateway 10.0.16.254  
dns-nameservers 10.0.1.48 10.0.1.54  
dns-domain iesmhp.local  
**2- Hacemos ina conexion remota desde gitbash con el comando ssh cristian@10.0.16.239**  
**3-Instalamos el paquete de ruby**  
sudo apt-get install ruby-full build-essential zlib1g-dev.  
**4- Instalamos los paquetes de gemas para poder usar jekyll.**  
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc  
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc  
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc  
gem install jekyll bundler  
**5- Conectamos nustro repositorio de github**  
mkdir myblog  
cd myblog  
git init  
git remote add origin https://cristian1502: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@github.com/cristian1502/myblog.git  
**6- Una vez conectado remotamente e instaladas las gemas lo arrancamos**  
bundle exec jekyll serve --host 10.0.16.239 --port 3000

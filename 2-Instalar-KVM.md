# Instalacion de KVM



### Requisitos

- Comenzamos buscando cuántas CPUs tenemos que soporten virtualización

```bash
grep -c "(svm|vmx)" /proc/cpuinfo
```

- En caso que usas una Maquina **VIRTUALBOX** para probar y instalar el KVM es necesario habilitar estas caracteristicas en tu maquina

- **Enable PAE/NX**
- **Enable Nested VT-x/AMD-v**

# foto
### Instalacion de KVM

- Para instalar el KVM es necesario instalar todos estos paquetes :

```bash
sudo apt install -y qemu-kvm libvirt-clients libvirt-daemon-system bridge-utils libguestfs-tools genisoimage virtinst libosinfo-bin virt-manager
```

- Ahora es necesario Comprobar el servicio libvirt :

```bash
systemctl status libvirtd
```

- Ahora Tenemos que agregar nuestro usuario al grupo de Administradores KVM :

1. Aseguramos que los grupos estan creados :

```bash
newgrp libvirt
newgrp libvirt-qemu 
```

2. Anadimos nuestro usuario a los grupos :

```bash
sudo adduser $(whoami) libvirt
sudo adduser $(whoami) libvirt-qemu
```

3. Tenemos que dar los permisos a KCM para utiliza el kernel de nuestra Maquina :

```bash
nano /etc/libvirt/qemu.conf
```

- Con "ctrl+w" buscamos por "user =" y asignamos estos cambios :

# foto


### Comprobacion :

- Nos logueamos como usuario y comprobamos que podemos ejecutar el comando virt-manager (inicia el gestor de máquinas virtuales)

```bash
virt-manager
```

- Tambien podemos Comprobar la instalacion con el siguiente comando : 
  
```bash
virt-host-validate
```


### COnfiguracion

```bash
virt-sysprep -d ANass --hostname ANass0 --root-password password:peque
```







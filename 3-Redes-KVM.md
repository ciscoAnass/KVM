# Redes en KVM

### Comandos 


| Parametro                  | Descripción                                        |
|----------------------------|----------------------------------------------------|
| virsh net-list             | Ver redes virtuales configuradas                   |
| virsh net-info <red>       | Ver Informacion de una red                         |
| virsh net-dumpxml <red>    | Obtener información sobre las redes (Fichero XML)  |
| virsh net-define <red.xml> | Definir una red virtual                            |
| virsh net-start <red>      | Iniciar una red virtual                            |
| virsh net-autostart <red>  | Iniciar automáticamente una red virtual            |
| virsh net-destroy <red>    | Editar una red virtual                             |
| virsh net-edit <red>       | Editar una red virtual                             |




### Configuración de una red tipo bridge estático


1. Accedemos al fichero /etc/network/interfaces (Debian)

> nano /etc/network/interfaces


2. Ponemos Nuestra Tarjeta Fisica en Modo Manual
   
```bash
auto enp0s3
iface enp0s3 inet manual
```

3. Configuramos la red Virtual que queremos Crear



```bash
auto br0
iface br0 inet static
bridge_ports enp0s3 
bridge_stp off
address 172.26.2.7
netmask 255.255.0.0 
network 172.26.0.0
gateway 172.26.0.1
broadcast 172.26.255.255
hwaddress ether 08:00:27:e7:41:51
```

4. Reninciamos el servicio Networking

```bash
systemctl restart networking.service
```

5. COmpronamos que La tarjeta virtual se ha creado Perfectamente


```bash
ip a show br0
```


### Configuración de un red tipo NAT



1. Accedemos al fichero /etc/network/interfaces (Debian)

> nano /etc/network/interfaces


2. Ponemos Nuestra Tarjeta Fisica en Modo Manual
   
```bash
auto enp0s3
iface enp0s3 inet manual
```

3. Configuramos la red Virtual que queremos Crear

```bash
auto br1
iface br1 inet dhcp
bridge_ports enp0s3 
bridge_stp off
bridge_fd 0
bridge_maxwait 0
```

4. Reninciamos el servicio Networking

```bash
systemctl restart networking.service
```

5. COmpronamos que La tarjeta virtual se ha creado Perfectamente


```bash
ip a show br0
```
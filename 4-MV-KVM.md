# Instalar Máquina Virtuales en KVM


## Comnado para instalar una maquina Virtual KVM

```bash
virt-install --connect qemu:///system --virt-type kvm --name Win10Anass --cdrom /var/lib/libvirt/iso/Win10_22H2_Spanish_x64v1.iso --osinfo detect=on --disk size=25 --memory 2048 --vcpus 1
```


## Parametros Obliigatorios
| Parametro  | Descripción |
|----------|----------|
|  --name               | NOmbre de la máquina Virtual                       |
|  --virt-type          | Tipo de virtualizacion que por defecto seria kvm   |
|  --cdrom              | La imagen ISO                                      |
|  --osinfo detect=on   | La variante del S.O que nos vamos a utilizar (Deteccion Automatica)       |
|  --disk size=25       | Capacidad del dico (25GB en este caso)             |
|  --memory 2048        | Cantidad de la Memoria RAM (2GB en este caso)      |
|  --vscpus 1           | Cantidad de vCPU (en este caso 1)                  |

## Parametros Adicionales

| Parametro  | Descripción |
|----------|----------|
|  --vnc              | Permite acceso a la interfaz gráfica mediante VNC                       |
|  --netowrk          | Configuración de red de la máquina virtual                              |
|  --graphics         | Configuración del tipo de gráficos (por ejemplo, VNC o SPICE)           |
|  --autostart        | Iniciar la máquina virtual automáticamente al arrancar el hipervisor     |
|  --os-variant       | La variante del S.O. que se va a utilizar |
|  --keymap es        | Elegir el lenguaje usado por el teclado de la maquina (es) |
|  --hvm              | Utilizar full-virtualization |


## Comandos Importantes

1. Para ver la lista de variantes

```bash
virt-install --osinfo list
```

2. virsh list

```bash
virsh list
```


3. Solicitar informaciones sobre la máquina :

```bash
virsh dominfo $Nombre_de_maquina
```


4. Datos del host KV/QEMU :


```bash
virsh dominfo $Nombre_de_maquina
```
5. Apagar la máquina:

```bash
virsh shutdown $Nombre_de_maquina
```

6. Forzar el apagado de una máquina:

```bash
virsh destroy $Nombre_de_maquina
```


7. Pausar la ejecución de una máquina :

```bash
virsh suspend $Nombre_de_maquina
```


8. Resumir, continuar con la ejecución de una máquina virtual: 

```bash
virsh resume $Nombre_de_maquina
```


9.  Eliminar una máquina virtual definitivamente : 

```bash
virsh undefine --remove-all-storage  $Nombre_de_maquina
```

10. Obtener la definicion XML de una maquina virtual :

```bash
virsh dumpxml $Nombre_de_maquina
```


# Gestion de Volúmenes Logicos


### 1. Listar volúmenes en el pool `default` : 

```bash
virsh vol-list default
```

### 2. Listar volúmenes en el pool default con detalles

```bash
virsh vol-list default --details
```

### 3. Ver información detallada de un archivo qcow2

```bash
virsh vol-info Mint-Anass.qcow2 default
```

### 4. Ver el archivo XML de la máquina

```bash
virsh vol-dumpxml Mint-Anass.qcow2 default
```

### 5. Crear un nuevo disco en el pool default

```bash
virsh vol-create-as --pool default --format qcow2 disco1.qcow2 1G
```

### 6. Añadir un disco a una máquina virtual

```bash
virsh attach-disk Win10Anass --source /var/lib/libvirt/images/disco1.qcow2 vdb --persistent --subdriver qcow2

```

### 7. Aumentar la capacidad de un disco

```bash
virsh vol-resize disco1.qcow2 20G --pool default
```

### 8. Clonar un disco


```bash
virsh vol-clone --pool default disco1.qcow2 disco1-clone.qcow2

```


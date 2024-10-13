# Storage pool en KVM

### Gestion de Volumenes Logicos

| Parametro                  | Descripción                                       |
|----------------------------|---------------------------------------------------|
| virsh pool-list            | Listar volúmenes de almacenamiento activos        |
| virsh pool-info $N-Vol     | Obtener información sobre el volumen físico       |
| virsh pool-dumpxml $N-Vol  | Obtener el fichero XML sobre un volumen físico    |
| virsh pool-edit $N-Vol     | Editar las características del volumen            |
| virsh vol-list $N-Vol      | Listar todos los discos virtuales                 |
| virsh pool-list  --all     | Liste los pools de almacenamiento definidos       |
| virsh pool-destroy         | Detenga el pool de almacenamiento                 |
| virsh pool-undefine        | Elimine la definición del pool de almacenamiento  |



## Creación de un Pool de Almacenamiento con Virsh


1. **Listar los pools de almacenamiento disponibles:**

- Primero Accedemos al directorio **/etc/libvirt/storage**
  
```bash
cd /etc/libvirt/storage
virsh pool-list
```

2. Ver la información de un pool existente (por ejemplo, default):

```bash
virsh pool-info default
```

3. Copiar la configuración del pool default a un nuevo archivo llamado **Mypool.xml**:

```bash
virsh pool-dumpxml default > MyPool.xml
```

# FOTO

4. Crear el directorio para el nuevo pool de almacenamiento:
  
 ```bash
 mkdir /var/lib/libvirt/Mypool.xml
```

5. Definir el nuevo pool de almacenamiento utilizando el archivo Mypool.xml:

```bash
virsh pool-define lunes.xml
```

6. Iniciar el nuevo pool de almacenamiento:

```bash
virsh pool-start lunes
virsh pool-autostart lunes
```

# Comandos Importantes


### Acciones para Máquinas Virtuales

| Parametro                  | Descripción                        |
|----------------------------|------------------------------------|
| virsh start $N-Maquina     | Iniciar una máquina virtual        |
| virsh suspend $N-Maquina   | Suspender una máquina virtual      |
| virsh resume $N-Maquina    | Reanudar una máquina virtual       |
| virsh reboot $N-Maquina    | Reiniciar una máquina virtual      |
| virsh shutdown $N-Maquina  | Apagar una máquina virtual         |
| virsh destroy $N-Maquina   | "Matar" una máquina virtual        |


### Gestionar MV  
| Parametro                           | Descripción                         |
|-------------------------------------|-------------------------------------|
| virsh define $N-Maquina             | Definir una máquina virtual         |
| virsh undefine $N-Maquina           | Borrar una máquina virtual          |
| virsh autostart $N-Maquina          | La maquina se inicie automaticamente|
| virsh -disable autostart $N-Maquina | Deshabilitar el comando anterior    |



### Consultar Informaciónes para MV
| Parametro                  | Descripción                            |
|----------------------------|----------------------------------------|
| virsh list                 | Listar MV running                      |
| virsh list -all            | Listar todas la MV                     |
| virsh dominfo $N-Maquina   | Obtener información sobre una máquina  |
| virsh vcpuinfo $N-Maquina  | Ver CPU máquina                        |


### Gestion de Pool

| Parametro                  | Descripción                                       |
|----------------------------|---------------------------------------------------|
| virsh pool-list     | Listar volúmenes de almacenamiento                       |
| virsh pool-info $N-Vol     | Obtener información sobre el volumen físico       |
| virsh pool-edit $N-Vol     | Editar las características del volumen            |
| virsh vol-list $N-Vol      | Listar todos los discos virtuales                 |
| virsh pool-list  --all     | Liste los pools de almacenamiento definidos       |
| virsh pool-destroy         | Detenga el pool de almacenamiento                 |
| virsh pool-undefine        | Elimine la definición del pool de almacenamiento  |



### Gestion de Red

| Parametro                  | Descripción                                        |
|----------------------------|----------------------------------------------------|
| virsh net-list             | Ver redes virtuales configuradas                   |
| virsh net-dumpxml <red>    | Obtener información sobre las redes (Fichero XML)  |
| virsh net-define <red.xml> | Definir una red virtual                            |
| virsh net-start <red>      | Iniciar una red virtual                            |
| virsh net-autostart <red>  | Iniciar automáticamente una red virtual            |
| virsh net-destroy <red>    | Editar una red virtual                             |
| virsh net-edit <red>       | Editar una red virtual                             |
# Pasos para instalar homestead 
> Pagina Oficial Por el momento -> [Guia para instalar ](https://laravel.com/docs/8.x/homestead)

## Comandos Fundamentales vagrant 
- vagrant list-commands
- autocomplete    manages autocomplete installation on host
- box             manages boxes: installation, removal, etc.
- cap             checks and executes capability
- cloud           manages everything related to Vagrant Cloud
- destroy         stops and deletes all traces of the vagrant machine
- docker-exec     attach to an already-running docker container
- docker-logs     outputs the logs from the Docker container
- docker-run      run a one-off command in the context of a container
- global-status   outputs status Vagrant environments for this user
- halt            stops the vagrant machine
- help            shows the help for a subcommand
- init            initializes a new Vagrant environment by creating a Vagrantfile
- list-commands   outputs all available Vagrant subcommands, even non-primary ones
- login
- package         packages a running vagrant environment into a box
- plugin          manages plugins: install, uninstall, update, etc.
- port            displays information about guest port mappings
- powershell      connects to machine via powershell remoting
- provider        show provider for this environment
- provision       provisions the vagrant machine
- push            deploys code in this environment to a configured destination
- rdp             connects to machine via RDP
- reload          restarts vagrant machine, loads new Vagrantfile configuration
- resume          resume a suspended vagrant machine
- rsync           syncs rsync synced folders to remote machine
- rsync-auto      syncs rsync synced folders automatically when files change
- snapshot        manages snapshots: saving, restoring, etc.
- ssh             connects to machine via SSH
- ssh-config      outputs OpenSSH valid configuration to connect to the machine
- status          outputs status of the vagrant machine
- suspend         suspends the machine
- up              starts and provisions the vagrant environment
- upload          upload to machine via communicator
- validate        validates the Vagrantfile
- version         prints current and latest Vagrant version
- winrm           executes commands on a machine via WinRM
- winrm-config    outputs WinRM configuration to connect to the machine


## Paso 1: Instalamos Virtual box y Vagrant y git .exe 
- https://www.virtualbox.org/wiki/Downloads
- https://www.vagrantup.com/downloads
- https://git-scm.com/downloads

## Paso 2: Ejecutamos el primer comando en una consola de windows ejemplo power shell o consola de git bash
- `vagrant box add laravel/homestead` -> Debes ejecutar este comando en tu cuenta de  usuario  *C:\Users\<tuCuentaUsuario>* 
- Este comando genera la carpeta .VirtualBox -> En caso de falla podemos borrar esta carpeta y ejecutar el comando de nuevo
- Nos pedira elegir que virtualizador estamos usando debemos escoger para este caso el virtual box. 
- Esperamos que se descargue es mas de **un GB de data** Yo espere 15 min. Imagen de exito de la ejecución del comando. 

![Respuesta Exitosa](./info/Instalación_hometead_paso_2.png)

## Paso 3: Debemos ir a nuestro directorio de windows y ejecutar el siguiente comando. 
- `git clone https://github.com/laravel/homestead.git ~/Homestead`   Esto lo que hace es clonar el repositorio de homestead pero hay que hacerlo en esta ruta -> *C:\Users\TuUsuario\*  
- Es rapido no deberia causar algun detalle, checa la imagen de respuesta.

![Respuesta Exitosa](./info/Instalación_hometead_paso_3.png)

## Paso 4: Debemos entrar a la carpeta Homestead  y crear el .bat para windows o .sh para linux 
- Debemos crear un release para obtener la ultima versión estable. 
- Ejecutamos este comando -> `git checkout release` 
- Luego Ejecutamos este comando ojo valida en que consola estas antes ::: `bash init.sh` -> Consola de Linux `init.bat` -> consola de Windows, claro todo estando en el directorio *C:\Users\cuenc\Homestead*
- Es rapido no deberia causar algun detalle, checa la imagen de respuesta.

![Respuesta Exitosa](./info/Instalación_hometead_paso_4.png)

## Paso 5: Debemos configurar el archivo homestead.yaml
- Debemos abrir un editor de codigo para modificar este archivo se ecnuentra en esta ruta -> C:\Users\cuenc\Homestead
- Pero antes debemos crear llaves publicas y privadas de git ya que son esenciales para la ejecución de homestead
- Podemos ejecutar el siguiente comando 
```
- ssh-keygen -t rsa -b 4096 -C "email de github" -> Con esto creamos nuestra llave publica 
- eval "$(ssh-agent -s)" -> Para evaluar que hay un agente corriendo
- ssh-copy-id [email] -> Copiar ID SSH al agente -> si no funciona ssh-add ~/.ssh/id_rsa
- cd ~/.ssh -> Copiar llave publica
- cat id_rsa.pub -> llave publica 
```
- Luego de ejecutar los comando esta te creara en tu directorio usuario un archivo llamado .**id_rsa** 
- En nuestro archivo de configuracion homestead.yaml debemos poner ese nombre por lo general ya esta puesto pero debemos validar 

![Respuesta Exitosa](./info/Instalación_hometead_paso_5_6.png)

## Paso 6: Luego debemos configurar o mapear nuestros directorio donde existiran los proyectos a virtualizar 
- Recuerda esto se debe configurar en el archivo Homestead.yaml
```
folders:
    - map: C:\laragon\www\projVirtual -> Aqui ruta de tu proyecto local 
      to: /home/vagrant/code/projVirtual

```
- Es rapido no deberia causar algun detalle, checa la imagen de respuesta. 

![Respuesta Exitosa](./info/Instalación_hometead_paso_5_6.png)

## Paso 7: Iniciamos homestead ` vagrant up`
- Debes ejecutar este comando dentro del directorio `C:\Users\cuenc\Homestead` usando tu consola de comando favorita para mi caso use bach de git 
- Ejecutamos el siguiente comando ` vagrant up`  -> Este comando nos permite iniciar nustra maquina virtual 
- se ejecuta un proceso que dura unos 20 min, inicia validaciones y conexiones 
- Generalmente dura mucho el primer intento ya luego no dura tanto.
- Genera las maquinas virtuales en esta ruta `C:\Users\cuenc\VirtualBox VMs`

![Respuesta Exitosa](./info/Instalación_hometead_paso_7.png)


## Paso 8: Entramos a la maquina virtual  ` vagrant ssh`
- Debes ejecutar este comando dentro del directorio `C:\Users\cuenc\Homestead` usando tu consola de comando favorita para mi caso use bach de git 
- Ejecutamos el siguiente comando ` vagrant ssh`  -> Este comando nos permite entrar a la maquina virtual 
- Es rapido no deberia causar algun detalle, checa la imagen de respuesta.

![Respuesta Exitosa](./info/Instalación_hometead_paso_8.png)

- Desde esta linea comando puedes clonar o crear tu proyecto laravel y dicho nombre debe ser igual al que se le agrego al documento .yaml 

- PD: En caso que nos de error de permisos al ejecutar comando como rm, mv, cp, Etc, podemos darle un plus peligroso de darle super permisos
- PD2: Debemos entrar a la raiz de hometead y buscar este archivo y dentro de ese archivo en la linea 40
- PD3: Pega este linea `config.vm.synced_folder ".", "/vagrant", :extra => "dmode=777,fmode=666"`
- PD4: sino funciona pues me dio el Lukitown y pegue esa mendiga linea en todos lados dejo imagen adjunta. Luego de eso ya pude renombrar carpetas si no funciona la vieja confiable reinicia la PC. 

![Respuesta Exitosa](./info/Instalación_hometead_paso_9.png)


## Paso 8: Luego de generar el proyecto debemos registrar el dominio. 
- Debemos al archivo .yaml y en la sección de site debemos apuntar al directorio `public` de tu proyecto. 
- Como ejemplo podemos hacerlo asi .
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
```
sites:
    - map: homestead.test -> Como lo veras en el navegador 
      to: /home/vagrant/code/projVirtual/cvsadminApp/public - Debe apuntar a tu index por eso redirecionamos a public 
```

- Debemos confirar  el archivo host para que pueda funcionar en nuestro local los DNS
- Si estas en windows ->  `C:\Windows\System32\drivers\etc`
- Si estas en Linux   ->  `etc/hosts`
- PD: en el pricipio del archivo .yaml esta la dirección ip de la maquina virtual es el que usaras para tu host
- PDX2: si cambiaste en el archivo .yaml la ruta debes ejecutar este comando para que tome los nuevos cambios `vagrant reload --provision`
- PDX3: si deseas apagar tu maquina virtual con el comando  `vagrant halt`
- PDX3: si deseas encender tu maquina virtual con el comando  `vagrant up`


## Paso 9: Si falla todo vuelves empezar 
- Para este caso borre la carpeta Homestead y empece desde el paso #2
 
## Lista de errores lo solucione con el paso 9: 

- Si usas la interfaz GUI  de VirtualBox de Homestead 

 `
	Usuario: vagrant 
	Pass: vagrant 
 ` 


- Si te sale este error prueba agregando este tag de codigo en el Vagrantfile 
```

If the box appears to be booting properly, you may want to increase the timeout ("config.vm.boot_timeout") value.
```

`
	config.vm.provider "virtualbox" do |vb|
	   vb.gui = true
	end	
`


- Esto me salio luego del comando vagran up solo reinicie y se acomodo 

```
Timed out while waiting for the machine to boot. This means that
Vagrant was unable to communicate with the guest machine within
the configured ("config.vm.boot_timeout" value) time period.

If you look above, you should be able to see the error(s) that
Vagrant had when attempting to connect to the machine. These errors
are usually good hints as to what may be wrong.

If you're using a custom box, make sure that networking is properly
working and you're able to connect to the machine. It is a common
problem that networking isn't setup properly in these boxes.
Verify that authentication configurations are also setup properly,
as well.

If the box appears to be booting properly, you may want to increase
the timeout ("config.vm.boot_timeout") value.
```

- Esto me salio luego de aplicar el comando vagrant destroy 
```
The name of your virtual machine couldn't be set because VirtualBox
is reporting another VM with that name already exists. Most of the
time, this is because of an error with VirtualBox not cleaning up
properly. To fix this, verify that no VMs with that name do exist
(by opening the VirtualBox GUI). If they don't, then look at the
folder in the error message from VirtualBox below and remove it
if there isn't any information you need in there.

VirtualBox error:

VBoxManage.exe: error: Could not rename the directory 'C:\Users\cuenc\VirtualBox VMs\ubuntu-20.04-amd64_1637867094859_3704' to 'C:\Users\cuenc\VirtualBox VMs\homestead' to save the settings file (VERR_ALREADY_EXISTS)
VBoxManage.exe: error: Details: code E_FAIL (0x80004005), component SessionMachine, interface IMachine, callee IUnknown
VBoxManage.exe: error: Context: "SaveSettings()" at line 3265 of file VBoxManageModifyVM.cpp

```


Hoy tuve el mismo problema en macOS 10.12 y perdí 6 horas tratando de encontrar una solución. Finalmente, después de varias reinstalaciones, reinicios y prueba y error, de alguna manera logré que funcionara siguiendo estos pasos ...

Desinstale y vuelva a instalar por completo Vagrant, VirtualBox y Homestead.
Asegúrese de que la homestead-7caja esté apagada dentro de la interfaz de usuario de VirtualBox
Haga clic con el botón derecho en el homestead-7cuadro y elija Configuración
Haga clic en 'Red'
En 'Adaptador 1', que debe conectarse a NAT, haga clic en 'Avanzado'
Marque la casilla junto a 'Cable conectado'
Guarde la configuración y reaprovisione Homestead con vagrant up --provision
Ejecutar vagrant reload --provisionpara reaprovisionar la máquina
¡Eso debería ser! Pude conectar SSH después de esto, pero no pude ver los sitios de Homestead a través del navegador (a pesar de que había configurado el /etc/hostsarchivo), pero un simple reinicio de la Mac pareció solucionar esto.

Dado que no sé exactamente qué causó esto en primer lugar, esto podría ser un poco de suerte para mi caso, pero avíseme cómo le va.



Abra el símbolo del sistema como administrador. Escribe el bcdeditcomando. Puede encontrar hypervisorlaunchtype Auto. Si ese es el caso, escriba bcdedit /set hypervisorlaunchtype offpara apagarlo. Reinicie y vuelva a intentarlo.

Espero que esto ayude.
## configurar postgresql virtual box 
https://billmartin.io/blog/2018/04/29/configure-laravel-to-use-postgresql-with-homestead/
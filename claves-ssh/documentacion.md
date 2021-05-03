# Autenticación en servidores de la nube
## Institut Joan D'austria

# Alumno: Daniel Domínguez
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@   ________        _  ____              ___              ___       ___  ____     @
@   `MMMMMMMb.     dM. `Mb(      db      )d'              `MMb     dMM' 6MMMMb    @
@    MM    `Mb    ,MMb  YM.     ,PM.     ,P                MMM.   ,PMM 6M'  `Mb   @
@    MM     MM    d'YM. `Mb     d'Mb     d'  ____          M`Mb   d'MM MM    M9   @
@    MM     MM   ,P `Mb  YM.   ,P YM.   ,P  6MMMMb         M YM. ,P MM YM.  ,9    @
@    MM     MM   d'  YM. `Mb   d' `Mb   d' MM'  `Mb        M `Mb d' MM  YMMMMb    @
@    MM     MM  ,P   `Mb  YM. ,P   YM. ,P       ,MM        M  YM.P  MM  6'  `Mb   @
@    MM     MM  d'    YM. `Mb d'   `Mb d'      ,MM'        M  `Mb'  MM 6M    MM   @
@    MM     MM ,MMMMMMMMb  YM,P     YM,P     ,M'           M   YP   MM MM    MM   @
@    MM    .M9 d'      YM. `MM'     `MM'   ,M'             M   `'   MM YM.  ,M9   @
@   _MMMMMMM9_dM_     _dMM_ YP       YP    MMMMMMMM       _M_      _MM_ YMMMM9    @
@                                                                                 @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```
   
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

## Introducción

Para no requerir introducir una contraseña al realizar push a repositorios remoto lo recomendable es utilizar ssh o el protocolo de github. En esta documentación vamos a ver cómo configurar tu cuenta de github para que acepte las claves ssh que tienes en tu sistema operativo.

## Paso 1: Crear la clave privada y pública

```bash
cd ~/.ssh
ssh-keygen -o -t rsa -C "cf19daniel.dominguez@iesjoandaustria.org"
```

Nos pedirá si queremos darle otro nombre (hay que dar la ruta completa), en mi caso:

`/home/zebnat/.ssh/githubtpad`

Nos pedirá si queremos además una contraseña (passphrase), le damos a enter para dejarla vacía ya que no somos un banco.

Las claves estarán en `~/.ssh` comprobar usando `ls -la`.

## Paso 2: Subir la clave pública a los servicios en la nube

### Subir la clave pública a Github

Suponemos que ya tienes cuenta de Github.

En tu cuenta de github, buscar el menú de cuenta Settings `https://github.com/settings/profile`.

Dentro de Settings en el apartado SSH `https://github.com/settings/keys` crearemos una nueva dándole a NEW SSH `https://github.com/settings/ssh/new`.

Le ponemos un título en el campo `Title`.

En el campo `Key` pegaremos mediante copy paste nuestra clave pública que empieza por ssh-rsa.

Ejemplo: (La he retocado para romperla)

```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDZNn6ADz+ZNpeDHUPwFfGMmbhj7MwMghobfL2WMDzWBHc+MkViXoYR28Z9d4rSVazgQOTn4yWkGpMmJXkzUvVd9RALBiNsE4ctuS2bFpFF+iDH1YyL2DZMnLLCbMyiPZgDpvHevMnrocTXLkS8Lv21TKuEw4vZTF2ZtiVOe+MSvXcsr32g1Y+m9/awHJWR253kJR5rZyuxxD784ePV8imlU21a8c+zDUSji79pyJj5cwk7cmThXxDDLE8FWjbTRr1i1eo8suMEjWZhK1/3FXU9VDEGK4ItWFxk8TSEa1ZTxu4uyKRLoPJuC+VfIsbbMsDDLdht2XivgTho7x5K14pkviiOTjnyJ8xGRxw4Pc9ZAUXzt87KYGvvuvMo3wjAeEASdUXNviMTUbJYukl23yKUDMYU5MpaASgNSQgU3fF4IPgU2yKfFD9YNwEiKI+CFKAKV0btsbazJV/QLUh0SUs9LEesha5T1Vbwb7Wo8GgFN6NEsy8hbMSse05Al2pgdu8Je+iDufocclEDVn81HzgW2P+NHcHlhiA8hUSkjhUhBKmvndRihgnDvNqMflTjbEawxYIgDo8QpnHCZrCs8ZbrJkp7cyR5unQui0KSlhFG/RyXubIIuquCioslUx5hEo2szcj7OQlhdab5nKIZxdxemL9pqN7JZv1dq3UVM6XdQ== zebnat@gmail.comHWJDEw24
```

### Subir la clave pública a Bitbucket

Asumiremos que ya tienes cuenta en Bitbucket.

Dale click a tu avatar y luego a `Personal Settings` o `https://bitbucket.org/account/settings/`.

Entra a SSH Keys `https://bitbucket.org/account/settings/ssh-keys/` y dale a new key.

Igual que en github en el paso anterior, ponle un título y copia y pega la public key en el campo `Key`.

## Paso 3: Clonamos un repositorio limpio con ssh

Antes de esto hay que utilizar ssh-agent para añadir la clave privada al agente. Si quieres probar y ver como no funciona aún utiliza el comando git clone.

`git clone git@github.com:daniel-dominguez-daw/m8-uf-git.git`

No te debería dejar todavía.

### Añadir con ssh-agent la clave privada para que la detecte

```bash
#obtiene el pid
eval `ssh-agent`
ssh-add ~/.ssh/githubtpad
```

### Clonando el repositorio de github mediante ssh

Ahora sí debería funcionar el comando de clone del dominio github.

Ejecutar: `git clone git@github.com:daniel-dominguez-daw/m8-uf-git.git`

### Clonando el repositorio de bitbucket mediante ssh

Asumiremos que has creado un repositorio en Bitbucket.

Ejecutar `git clone git@bitbucket.org:daniel-dominguez-daw/m8-ssh-test.git`


Log del resultado del comando funcionando correctamente:

```bash
[zebnat@zeb-arch ~]$ git clone git@bitbucket.org:daniel-dominguez-daw/m8-ssh-test.git
Clonando en 'm8-ssh-test'...
The authenticity of host 'bitbucket.org (104.192.141.1)' can't be established.
RSA key fingerprint is SHA256:zzXQOXSRBEiUtuE8AikJYKwbHaxvSc0ojez9YXaGp1A.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'bitbucket.org,104.192.141.1' (RSA) to the list of known hosts.
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0)
Recibiendo objetos: 100% (4/4), listo.
[zebnat@zeb-arch ~]$ 
```

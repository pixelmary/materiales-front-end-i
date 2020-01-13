# Instalación de ordenadores para el curso de Adalab

En el curso de programación front-end de Adalab necesitaremos usar un ordenador. Para poder realizar el curso de forma fluida, el ordenador debería tener estas características (no es obligatorio que las tenga, pero para que tengáis una orientación):

- Al menos 8GB de RAM (con 4GB irá algo más lento pero también se puede)
- Procesador i5 o similar con velocidad superior a 1GHz
- Disco duro: recomendamos desde 128GB; si es SSD va a ir más fluido que si es HDD pero se puede tener más capacidad por menos precio
- Tarjeta gráfica y pantalla: cualquiera pueden ir bien, aunque recomendamos pantalla de 15’ o como mínimo 13’ para poder programar junto a una compañera (con pantallas más pequeñas es posible pero se hace más complicado)

Para poder realizar el curso el sistema operativo (SO) del ordenador debe ser Linux o Mac, y no es posible realizarlo con Microsoft Windows. Si no tienes un Mac con OSX o un PC con Linux (recomendamos Ubuntu), en la siguiente sección te explicamos cómo instalarlo.

## Instalación de Ubuntu

En primer lugar, para los PCs que no tengan un sistema operativo Linux, recomendamos instalar Ubuntu. Tenemos 2 opciones:

- Instalar Ubuntu borrando todo lo que hay en el ordenador (recomendada): esta opción es obligatoria para equipos viejos que no tienen recursos para tener a la vez Windows y Linux.
- Instalar Ubuntu junto a Windows: crearemos una partición del disco duro del ordenador para instalar Ubuntu, y luego poder arrancar el ordenador desde el SO que elijamos; esta opción es más compleja y depende del ordenador concreto que tengáis que pueda hacerse o no.

> NOTA: Antes de proceder a la instalación es muy importante **hacer una copia de seguridad de los datos** que estén en el ordenador y que no queramos perder.

Usaremos la distribución de Ubuntu 18.04, que podemos descargar una ISO desde http://releases.ubuntu.com/18.04/ y grabaremos en un CD o pendrive. El día de la sesión de bienvenida os ayudaremos a instalarlo y llevaremos pendrives preparados con esta versión. Seguiremos los pasos de instalación para instalar y configurar el sistema.

Si queremos mantener Windows, tendremos que hacer una partición:

- Hacer partición e instalar Ubuntu siguiendo este tutorial (mínimo de 30GB): https://www.tecmint.com/install-ubuntu-alongside-with-windows/

> NOTA: Al elegir instalar ubuntu, seleccionamos la opción de "opciones adicionales" para elegir en qué partición hacerlo. Una vez seleccionada la partición donde instalar Ubuntu, elegir que el gestor de arranque (bootloader) se instale en el disco duro principal en un desplegable abajo de la pantalla.

### Problemas en la instalación de Ubuntu

En equipos de la marca MSI, [suele haber problemas con los drivers de teclado / ratón en la instalación, de la tarjeta gráfico y/o de la conexión WiFi](https://gist.github.com/mari-linhares/cef4cb3440408e44963d1447a7db5ae0).

En algunos Asus, no funciona la conexión Wifi, y [hay que instalar los drivers](https://askubuntu.com/questions/990378/wi-fi-not-working-on-lenovo-thinkpad-e570-realtek-rtl8821ce) que podéis pasar en un pendrive o con una conexión a Internet a través de vuestro móvil.

También encontramos otras incompatibilidades de hardware (ordenador) con Ubuntu, [como esta que nos ha sucedido](https://askubuntu.com/questions/38780/how-do-i-set-nomodeset-after-ive-already-installed-ubuntu).

## Instalación de los programas

Una vez preparado el sistema, instalaremos algunos programas para el curso. En Ubuntu los podemos instalar con la interfaz visual (instalador de programas) o desde la terminal usando `apt-get install`. En Mac, recomendamos usar [homebrew](https://brew.sh/) para instalar desde la terminal.

### Instalación de Node JS

Desde **Ubuntu** ejecutad las siguientes líneas en la terminal de una en una:

```bash
sudo apt install curl
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt install nodejs
```

Para más información [consultar esta página](https://joshtronic.com/2018/05/08/how-to-install-nodejs-10-on-ubuntu-1804-lts/).

Desde **Mac** ejecutad las siguiente línea en la terminal de una en una:

```bash
sudo brew install node@10
```

Una vez terminada la instalación debemos comprobar que todo ha ido bien. Para ello ejecutaremos en la terminal la siguiente línea:

```bash
node --version
```

Y la terminal debe mostrar la versión de Node JS instalada, algo como `v10.14.0`.
Si por el contrario la terminal muestra el mensaje `No se ha encontrado la orden «node»...` es que algo hemos hecho mal.

### Instalación de Git

Queremos instalar la versión 2.x, para lo cual debemos seguir el [manual de esta página](https://git-scm.com/downloads).

Desde **Ubuntu** ejecutad las siguientes líneas en la terminal de una en una:

```bash
sudo apt update
sudo add-apt-repository ppa:git-core/ppa
sudo apt install git
```

También debemos comprobar que Git se ha instalado correctamente la versión 2.x escribiendo en la terminal la siguiente línea:

```bash
git --version
```

### Otros programas

Desde el instalador visual, podremos instalar el resto (última versión de todos):

- VSCode (https://code.visualstudio.com/)
- Chrome (https://www.google.com/chrome/)
- Slack (https://slack.com/)

También crearemos cuentas en estos servicios (elegid un nombre de usuario teniendo en mente que será parte de vuestro perfil profesional):

- GitHub (https://github.com/)
- Trello (https://trello.com/)

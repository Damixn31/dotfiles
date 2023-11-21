# Instalacion de zsh con Oh My Zsh

- Esta guia proporciona instruscciones pasos para instalar Zsh configurarlo con Oh My Zsh en el sistemas.

## Instalacion de Zsh

1. **Verificar la existencia de Zsh:**
```bash
zsh --version
```

2. Actualizacion e instalacion:
```bash
sudo pacman -Syu && sudo pacman -S zsh
```

3. Cambiar tu shell preterminado a Zsh:
```bash
chsh -s $(which zsh)
```

4. Instalar Oh My Zsh
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Configuracion de temas y plugins de Oh My Zsh
[Cambiar de Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)
- Instalacion de zsh-autosuggestions y zsh-syntax-highlighting
```bash
paru -S zsh-autosuggestions zsh-syntax-highlighting
```

## Fichero de configuracion de Zsh (.zshrc)
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

# Nota: 
- si de alguna manera no nos reconoce el zsh-syntax-highlighting y zsh-autosuggestions instalamos locate para saber dondes esta ubicado  

```bash
sudo pacman -Syu && sudo pacman -S locate
```

1. Actualizamos nuestra db
- Para sincronizar todos los ficheros existentes en el sistema.

```bash
sudo updatedb
```

2. hacemos un locate a nuestros plugins
```bash
locate zsh-autosuggestions
locate zsh-syntax-highlighting
```

## Agregamos plugins a nuestro a nuestro fichero (.zsh) segun lo que nos muestre donde esta con locate

# EJEMPLO:
source /usr/share/zsh/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
source /usr/share/zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

## sudo plugins
- Para que cuando presionemos doble Esc nos ponga directamente el sudo en nuestra terminal 

1. estando como root creamos un directorio en (/usr/share)
```bash
mkdir zsh-sudo
```
2. asignamos como propietario y grupo a nuestro usuario

- Para ver tu nombre de usuario y grupo
```bash
id nombre_usuario
```
```bash
chown usuario:grupo zsh-sudo
```

3. Salimos de usuario root y entramos a nuestro directorio de zsh-sudo
```bash
cd /usr/share/zsh-sudo
```
4. Con wget nos descargamos el enlace

```bash
wget https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/plugins/sudo/sudo.plugin.zsh
```

5. agregamos en nuestro fichero (.zshrc)

source /usr/share/zsh-sudo/sudo.plugin.zsh




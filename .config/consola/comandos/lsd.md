# lsd
- Es un reemplazo moderno para el comando "ls" en sistemas Unix. "ls" se utiliza para listar el contenido de un directorio, y "lsd" mejora la salida y añade algunas características adicionales.

## Características
- Colores y estilos mejorados para una salida más legible.
- Íconos para representar tipos de archivos.
- Soporte para árboles de directorios.

## Instalacion 

```bash
sudo pacman -Syu && sudo pacman -S lsd
```

## Configuracion en nuestro fichero (.zshrc)

alias ls='lsd'

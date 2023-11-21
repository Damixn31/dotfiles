# scrub
- se utiliza para realizar la limpieza segura (scrubbing) de datos en dispositivos de almacenamiento, especialmente en discos duros y SSDs. Su función principal es realizar la verificación y corrección de errores en los datos almacenados en el disco, con el objetivo de mantener la integridad de los datos y prevenir la pérdida de información debido a posibles errores de lectura o escritura.

## Instalacion

```bash
sudo pacman -Syu
paru -S scrub
```

## uso

```bash
scrub nombreFichero.txt
```

# shred 
-  se utiliza para sobrescribir y eliminar de manera segura archivos o dispositivos. La principal función de shred es garantizar que los datos originales no sean recuperables después de que el archivo ha sido eliminado. Se utiliza comúnmente para eliminar información sensible y confidencial.

## Instalacion

```bash
sudo pacman -Syu && sudo pacman -S coreutils
```

# uso 
```bash
shred -u -n 10 -v archivo_secreto.txt
```

## Configuracion de los en nuestro fichero (.zshrc)
- Creamos una funcion 

rmk () {
  scrub -p dod $1
  shred -u -n 10 -v $1
}

# Entornos de Programación. Unidad 2

**Ejercicio 7.12:**
```
man -f date
```
```
man -f cal
```
```
date
```
```
cal
```

**Ejercicio 7.13:**
```
man --help clear
```

**Ejercicio 7.14:**
```
echo -e "hola\nqtal"
```
```
echo -e "hola\tqtal"
```
```
echo -e "hola\bqtal"
```
```
echo -e "hola\rqtal"
```

**Ejercicio 7.15:**
- Ctrl + A -> Vuelve hacia atras todo
- Ctrl + E -> Va hacia adenalte todo
- Ctrl + K -> Borra todo lo que este a la derecha del cursor
- Alt + D -> Borra a la derecha del cursor hasta un espacio
- Ctrl W -> Como Alt + D pero hacia la izquierda.

**Ejercicio 7.16:**
```
echo ~
```
Imprime la ruta del directorio personal del usuario

```
echo \~
```
Imprime ~

```
echo \\~
```
Imprime \~

**Ejercicio 7.17:**
Info provee una descripcion super detallada del comando y help una resumida.

**Ejercicio 7.18:**

**Ejercicio 7.54**
```
mkdir test
```
Lo creo con el nombre test.

```
ls
```
Veo los archivos y directorios dentro del directorio actual para chequear que este

```
cd test
```
Voy al directorio nuevo.

```
cd ..
```
Vuelvo al directorio anterior

```
rmdir test
```
Lo elimino

**Ejercicio 7.55**

```
cd /
```
Voy al directorio raiz (/)

```
cd /usr/local/bin
```
Esto es ruta absoluta porque incluye la primer /, refiriendoce a la raiz.

```
cd usr/local/bin
```
Esto es relativa porque no agrego el directorio actual en la ruta al principio (/).

**Ejercicio 7.56**
```
mkdir carpeta
touch carpeta/archivo
rmdir carpeta
```
Se produce error porque el directorio carpeta no esta vació y rmdir solo sirve para eliminar directorios vacios.

**Ejercicio 7.57**
```
touch carpeta
rmdir carpeta
```
Se produce error porque touch crea un *archivo* llamado carpeta, pero rmdir solo elimina directorios, no archivos.

**Ejercicio 7.58**
```
mkdir carpeta1/carpeta2
```
Esto pasa porque la ruta *carpeta1/carpeta2* aun no existe.
Para solucionarlo se podría hacer:
```
mkdir carpeta1 carpeta2
mv carpeta2 carpeta1
```
Creo ambas carpetas en el mismo directorio y después muevo la 2 dentro de la 1.

**Ejercicio 7.59**
```
mkdir carpeta1 carpeta1
```
Crea los dos directorios (carpeta1 y carpeta2) en el directorio actual

```
mkdir "carpeta1 carpeta2"
```
Crea un directorio llamado carpeta1 carpeta2 con espacio en el medio.

**Ejercicio 7.60**
```
touch a1 a2
mkdir c1
mv a1 c1
mv a2 c1
ls
cd c1
ls
```

**Ejercicio 7.61**
```
mkdir ej
cd ej
touch argentina francia
mkdir semi1 semi2
cd semi1
touch argentina croacia
cd ../semi2
touch francia marruecos
cd ../..
```

**Ejercicio 7.62**
```
cp -r ej/ ejcopia
```

**Ejercicio 7.63**
```
rm -r ej ejcopia
```

**Ejercicio 7.64**
```
ls -a
```

**Ejercicio 7.71**
```
rm *~
rm *#
rm *.*
```

**Ejercicio 7.72**
```
ls *[A-Z]*
```

**Ejercicio 7.82**
```
mkdir {1..999}
```

**Ejercicio 7.84**
```
cd /bin 
pwd
```
Mostrará la ruta del directorio actual

```
pwd -P
```
Mostrará la ruta del directorio actual sin enlaces simbólicos

**Ejercicio 7.86**
```
mkdir ej
ln -s ej enlace
cd enlace
rmdir ej
cd enlace
```
Se rompe por que no existe el directorio al cual enlace hace referencia

**Ejercicio 7.87**
```
ln -s usr/bin /bin
```
El primer carácter l en lrwxrwxrwx confirma que es un enlace simbólico.

**Ejercicio 7.88**
```
mkdir -p ~/carpeta/destino
cd ~/carpeta
ln -s destino enlace
mv enlace ..
cd ../enlace
```
Esto da error ya que al crearse enlace, este apunta a ~/destino (ya que cuando creamos el enlace, este apunta a la ruta relativa desde donde lo creamos hasta el archivo que queremos enlazar).
Entonces, al ~/destino no existir, da error. En definitiva, el error reside en crear el enlace parados en el directorio carpeta y no en ~.

Para crear el enlace se tuvo que haber hecho: (Desde el directorio ~)
```
ln -s carpeta/destino enlace
```

**Ejercicio 7.91**
Hay 4 particiones en el sistema (sda1, sda2, sdb1, sdb2), 2 unidades de almacenamiento (sda, sdb), la partición sdb1 se monto usando:
```
sudo mount /dev/sdb1 /mnt
```
El gestor de arranque se encuentra en la partición sda1.

**Ejercicio 7.92**
```
find . -type f -name "*.txt" -exec mv {} docs/ \;
```











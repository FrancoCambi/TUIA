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






**Ejercicio 7.128**
```
nano ej
cat ej
```

**Ejercicio 7.129**
```
nano ej2
cat ej ej2
```

**Ejercicio 7.135**
El error se debe a que sort ordena de forma lexicográfica por defecto.
La solución seria usar la bandera -n para ordenar de forma numérica.
```
sort -n numeros
```

**Ejercicio 7.136**
Por que mundo y mundo no son consecutivas, para eliminarlas, se debería hacer:
```
sort archivo
uniq archivo
```

**Ejercicio 7.142**
```
cut -d "," -f 2 test
```

**Ejercicio 7.144**
No muestra Murinigo ya que entre el nombre y el apellido hay más de un espacio.

**Ejercicio 7.146**
- "xx"|"yx"
- "(xx)*"
- "x+"|"y+"
- "(x)(y+)"
- "(x+)y(x+)"
- "(a+)(.jpg)|(a+)(.jpeg)"

**Ejercicio 7.147**`
```
grep "\berror\b" ej.txt
```
```
grep "  " ej.txt
```
```
grep -E "[0-9]+" ej.txt
grep [0-9] ej.txt
```
```
grep -E "^#" ej.txt
```

**Ejercicio 7.148**
```
grep -E ";." ej.txt
```

**Ejercicio 7.149**
```
grep -E "[A-Z]{2}[1-9]{3}[A-Z]{2}" ej.txt
```

**Ejercicio 7.150**
```
grep -E "\b[1-9][0-9]\-[0-9]{3}-[0-9]{3}\b" ej.txt
```

**Ejercicio 7.151**
```
grep -Ew "[A-Z][a-z]*" ej.txt
```

**Ejercicio 7.152**
```
grep -Ewo "[[:alnum:]]+@[[:alnum:]]+\.[[:alnum:]]+" ej.txt
```

**Ejercicio 7.174**
```
cat * > ej.txt
```

**Ejercicio 1.175**
Lo que pasa es que se crea el archivo llamado 10 y se imprime "2" seguido de todos los nombres de todos los archivos y directorios
del directorio actual, seguido de un "3".

**Ejercicio 7.180**
```
sort -n ej.txt | head -n 1
```

**Ejercicio 7.181**
```
head -n 3 ej.txt | tail -n 1
```

**Ejercicio 7.182**
```
wc -l * | sort -nr | head -n 2 | tail -n 1
```

**Ejercicio 8.14**
```
chmod a-x *.py
```

**Ejercicio 8.15**
```
chmod a+r *.txt
```

**Ejercicio 8.17**
```
sudo useradd -m -s /bin/bash visitante
```

**Ejercicio 8.18**
```
sudo usermod -s /bin/bash visitante
```

**Ejercicio 8.20**
```
sudo mkdir /home/visitante
sudo chown visitante:visitante /home/visitante
sudo chmod 700 /home/visitante
```

**Ejercicio 9.37**
```
echo $PATH | tr ':' '\n'
```

**Ejercicio 9.38**
```
ls -lS | grep '^-' | head -n 1
```

Sin -s, no le asigna shell.
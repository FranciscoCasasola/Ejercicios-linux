# Ejercicios de linux

## Tema 3

### Ejercicio 1

Show all the jpg pictures in the current directory.

```console
ls *.jpg
```

### Ejercicio 2

Display all the files in the directory /usr/bin starting with letter "j"

```console
ls /usr/bin/j*

### Ejercicio 3

Show all the files in the directory /usr/bin/ starting with the letter "k", with an "a" in the 3rd place

```console
ls /usr/bin/k?a*

### Ejercicio 4

Show all the files in the directory /bin ending with "n"

```console
ls /bin/*n
```

### Ejercicio 5

Display all the files in the directory /etc and all the files in every subdirectory recursively.

```console
ls -R /etc
```

### Ejercicio 6

In your home directory, create another directory named test. Copy the file gzip from the directory /bin to test. Create a duplicate of gzip named gzip2 inside test.

```console
mkdir /home/alumno/test
cp /bin/gzip /home/alumno/test
co /bin/gzip /home/alumno/gzip2
```

### Ejercicio 7

Change the name of the directory test to test2. Create test3 at the same level in the directory tree as test2 and move all the files from test2 to test3. Delete test2.

```console
mv test test2
mkdir test3
mv test2 test3
rmdir test2
```

### Ejercicio 8

Create an empty file named "?Hello all?". Can you? Is it a good idea to name a file this way? Explain your answer.

Si, es posible crearlo, pero no se aconseja, puesto que caracteres como "?" son caracteres usados por el cmd, ademas se deberían poner muchas barras inversas "\" y seria mas posible cometer errores.

### Ejercicio 9

Create a directory named multimedia_test and copy all the content from the directory multimedia into it. Then, create two files in multimedia/video/, one named films.txt and another named actors.txt. Edit the file films.txt and write the title of your favourite movie. Then, create another file in multimedia_test/video/, also named films.txt. Edit this file and now write the titles of your five favourite movies. Copy of all the content of multimedia into multimedia_test ensuring that only most recently modified versions of files remain.To check that
everything is ok, check if multimedia_test/video contains the empty fileactors.txt and the file films.txt contains 5 titles and not 1.

```console
mkdir multimedia_test
cp -R /multimedia/* /multimedia_test/
cd multimedia/video/
touch films.txt actors.txt
mcedit films.txt
cd ../..
cd multimedia_test/video/
touch films.txt
mcedit films.txt
cd ../..
cp -R -u multimedia/* multimedia_test/
```

### Ejercicio 10

Delete the directory multimedia/pictures/others. The system must ask for confirmation.

```console
rmdir multimedia/pictures/other
```

### Ejercicio 11

Move the file films.txt, which is in multimedia/video, to the directory above, at the same time renaming the file to my_films.txt

```console
mv multimedia/video/films.txt multimedia/my_films.txt
```

# Ejercicios de Linux 

## Tema 4

### Ejercicio 1

654   		rw-r-xr--
766   		rwxrw-rw
777   		rwxrwxrwx
520  		r-x-w----
764   		rwxrw-r--
440   		r--r-----

### Ejercicio 2

Create the groups office1 and office2.

```console
sudo groupadd office1
sudo groupadd office2
```

### Ejercicio 3

Create the users gearoid and paul. These users must belong only to the group
office1.

```console
sudo adduser gearoid --ingroup office1
sudo adduser paul --ingroup office1
```

### Ejercicio 4

Create the users anna and emma. These users must belong only to the group office2.

```console
sudo adduser anna –ingroup office2
sudo adduser emma –ingroup office2
```

### Ejercicio 5

As user gearoid, create a file named topsecret.txt in his home directory. Only
this user must have access to this file, both for reading and writing.

```console
su gearoid
cd
touch topsecret
chmod 600 topsecret
```

### Ejercicio 6

Create another file named sales.txt, also as user gearoid,. All users in the same group as gearoid must have access to this file, both for reading and writing. The permissions for owner and the rest of users must remain as default. Check that you can modify the file if you access it as user paul.

```console
touch sales
chmod 664
```

### Ejercicio 7

As user anna, create a file named employees.txt. Any user must have access to
read its content and any user in the same group must have access to read or write to it.

```console
su anna
cd
touch employees
chmod 664 employees
```
### Ejercicio 8

Create the user student (if it is not yet created). Copy the file employees.txt to the home directory of user student . Change the owner and the group of this file to student.

```console
sudo adduser student
sudo cp employees.txt
cd /home/student
sudo chown student prueba.txt
```

### Ejercicio 9

As user paul, copy a program from the directory /usr/bin to the home directory
with a different name. For example, you can copy xclock with the new name myclock. Take a look at the permissions of this program. Check that you can execute it. Maybe you have to allow users to run programs in the graphic environment. To do that, type xhost + as administrador.






# 🐧 MEGACHULETA LINUX + BASH
https://github.com/miquel-manzanoITB/ChuletaBash/blob/main/README.md
## Shebang
`#!/bin/bash`

## Ejecutar scripts
```
chmod +x script.sh
./script.sh
bash script.sh
```

## Variables
```
var="hola"
echo "$var"
```

## Variables especiales
```
$0 nombre script
$1..$n parámetros
$# número de parámetros
$@ todos los parámetros
$? último código salida
$$ PID
```

## Funciones
```
func() {
  echo "Hola $1"
}
```

## Capturar resultado
`res=$(func arg)`

## Variables locales
`local var="valor"`

## Condicional if
```
if [ cond ]; then
elif [ cond ]; then
else
fi
```

⚠️ Espacios obligatorios en [ ]

## Operadores numéricos
```
-eq igual
-ne distinto
-gt mayor
-lt menor
-ge >=
-le <=
```
ex:
```
if [ $1 -eq 2 ]; then
   echo "Dos"
fi
```

## Comparar strings
```
= igual
!= distinto
-z vacío
-n no vacío
```

## Operadores de archivos
```
-f archivo
-d directorio
-e existe
-r lectura
-w escritura
-x ejecución
```

## AND / OR
```
[ cond ] && ok
[ cond ] || error
```

## Exit / return
```
exit 0 correcto
exit 1 error
return 1 función
```

## Leer input
`read -p "Texto: " var`

## Case
```
case $var in
  1) comando ;;
  *) error ;;
esac
```

## Bucles
```
for i in 1 2 3; do
done

while [ cond ]; do
done
```

## Redirecciones
```
> sobrescribe
>> añade
2> errores
```

## Pipes
`ls | grep ".sh"`

## Función error típica
```
error() {
  echo "Error: $1"
  exit 1
}
```

## Comandos básicos
```
pwd
ls -l -a
cd
touch
cp
mv
rm -r
mkdir
cat
less
head
tail
grep
find
whoami
id
ps aux
kill
chmod
date
```

## Directorios importantes
```
/ raíz
/home usuarios
/root root
/bin comandos
/sbin admin
/etc configuración
/var logs
/tmp temporales
/usr programas
/opt software externo
```

## /etc importantes
```
/etc/passwd usuarios (NO passwords)
/etc/shadow contraseñas
/etc/group grupos
/etc/hostname nombre máquina
/etc/hosts resolución local
/etc/fstab discos
/etc/sudoers permisos sudo
```

## /etc/passwd formato
`usuario:x:UID:GID:info:/home:/shell`

## Permisos chmod
```
rwx r-x r--
│   │   │
│   │   └── Otros (others)
│   └────── Grupo (group)
└────────── Usuario dueño (owner)
```
| Permiso  | Letra | Significado  |
| -------- | ----- | ------------ |
| Leer     | r     | leer archivo |
| Escribir | w     | modificar    |
| Ejecutar | x     | ejecutar     |
```
chmod u+x script.sh   # usuario
chmod g+w file.txt   # grupo
chmod o-r file.txt   # otros
chmod a+x script.sh  # todos
```
**Valores binarios**
| Permiso | Valor |
| ------- | ----- |
| r       | 4     |
| w       | 2     |
| x       | 1     |

**Funcionamiento:**
| Permisos | Binario | Decimal |
| -------- | ------- | ------- |
| ---      | 000     | 0       |
| --x      | 001     | 1       |
| -w-      | 010     | 2       |
| -wx      | 011     | 3       |
| r--      | 100     | 4       |
| r-x      | 101     | 5       |
| rw-      | 110     | 6       |
| rwx      | 111     | 7       |

ex:
`chmod 755 script.sh`

## Debug
`bash -x script.sh`

## Frases clave examen
```
- /etc/passwd no guarda contraseñas
- Bash usa echo en lugar de return
- Código 0 = éxito
- Espacios en [ ] son obligatorios
```

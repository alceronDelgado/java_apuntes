# java_apuntes Fundamentos del lenguaje Java

Apuntes de java de clase de algoritmia - ADSO 2843610

---

Declaración de variables
variables referenciadas
Métodos
Clases
Objetos
Herencia
Poliformismo
Sobrecarga de métodos.

---

Se llaman igual los Métodos pero sus argumentos son completamente diferentes.

```Java
public void printIn (int i)
public void printIn (float f)
public void printIn (String s,int i)
```

## Encapsulamiento

Oculta los campos implementados de la clase, para acceder a los datos de manera obligatoria se debe de crear una interfaz

## Excepciones

En caso de que hayan errores en el programa, se llama a la excepción, se representan por la clase Exception. Las palabras reservadas para usarlo son try, catch.

## Arreglos

Son estructuras de datos almacenados de manera bidimensional, permiten almacenamiento de un conjunto de alores en posiciones diferentes.

### Declaración, creación y uso de arreglos

> Declaración de arreglos
Para poder declarar los arreglos usamos la sentencia que se uso en el código siguiente:

```Java
int edad[]; //Arreglo de tipo entero llamado edad
int nota[];
String nombre[];
```

Después de declarar el arreglo, se debe crear, como si fuese un objeto, es como para evitar trabajar con ese arreglo declarado, como crearle una copia y trabajar con la copia, no el original.

> Creación de arreglo

Después de declar, se debe crear y se crea usando la palabra reservada new + la cantidad de posiciones que va a tener el array.

```Java
//Crear array
variable = new tipoDato[tamaño];

//Ejemplo
edad = new int[10]; //Creación del arreglo edad con 10 posiciones.
nota = new double[15]; //Creación del arreglo nota con 15 posiciones.
nombre = new String[3]; //Creación del arreglo nombre con 3 posiciones.
```

Podemos declarar y crear el arreglo al mismo tiempo en una sola línea de código.

```java
int edad[] = new Int[10]; //declaración y creación de un arreglo llamado edad de 10 posiciones de tipo entero.

int edad[0] = 10;
int edad[1] = 13;
int edad[2] = 22;
int edad[3] = 32;
int edad[4] = 42;
int edad[5] = 15;

for(i = 0;i<=edad -1;i++){
    System.out.println("la edad en el arreglo es"+edad[i]);
}

```

Podemos también declarar e inicializar el arreglo en la misma línea de código.

```Java
String nombres[]=('Pedro','Gonzalo','Joaquin','Alejandro','Kevin',)
```

### Recorrido de un arreglo

Se realiza un recorrido por medio de un ciclo.

¿Qué pasaría si se ejecuta el ciclo y recorre una posición adicional o una posición inexistente del arreglo?

marcaría un error, para ello usamos un un try y catch para capturar el error y terminar el programa.

Al intentar ejecutrar el programa y marca un error de tipo
ArrayIndexOutOfBoundsException = significa que el limite del array se paso

## For each

Es una forma más factible de recorrer el array.

```java
String nombre [] = ("persona#1","persona#2","persona#3","persona#4")
for (String x:nombre){ //lo que hace es que el valor de la posiión n del array se guarde en la variable x y así se imprime el valor.
    System.out.println(x);
}
```

```Java
package arreglos;
import javax.swing.*;
public class Arreglos {


public static void main(String[] args) {
 //1. Calcular el salario promedio de los empleados
 double salario[];//Declaración del arreglo de Salarios
 double sumSalario=0,salarioPromedio;
 int totalEmpleados, cantEmplSalSuperior=0;
 totalEmpleados=Integer.parseInt(JOptionPane.showInputDialog(null,”Ingrese cantidad de empleados”));
 salario= new double[totalEmpleados];//Creación del arreglo de Salarios
 for(int i=0;i<totalEmpleados;i++){
 //Lectura de cada posición (i) del arreglo (en cada posición se almacena un salario diferente
 salario[i]=Double.parseDouble(JOptionPane.showInputDialog(null,”Ingrese salario del empleado”));
 sumSalario=sumSalario+salario[i];
 }
 
 salarioPromedio=sumSalario/totalEmpleados;
 JOptionPane.showMessageDialog(null, “El salario promedio es “+salarioPromedio);
 //2. Determinar cuántos empleados ganan un salario superior al promedio
 for(int i=0;i<totalEmpleados;i++){
    //Uso del arreglo de salarios, previamente cargado en la línea 18
    if(salario[i] > salarioPromedio){
    cantEmplSalSuperior++;
    }
 }
}
}
JOptionPane.showMessageDialog(null, “El numero de empleados con salario superior al promedi es “+cantEmplSalSuperior); 
```

## Arreglos en los objetos

!TODO: por preguntarle al instructor, no entendí.

```java

//Primero creamos la clase de los objetos.



```java
public Class Alumno{
    private String nombre;
    private Int edad;

    public alumno(String nombre, Int edad){
        this.nombre = nombre;
        this.edad = edad;
    }

    public String getNombre(){
        return nombre;
    }

    public Int getEdad(){
        return edad;
    }
}

public Class application{
    
    public static void main(String[] args){
        //Aca lo que hacemos es invocar la clase y le creamos un objeto llamado estudiante, en realidad son 3 objetos pero de tipo estudiante.
        Alumno Estudiante[] = new Alumno[3];

        Estudiante[0] = ("Alejandro",23);
        Estudiante[1] = ("pedro", 17);
        Estudiante[2] = ("gomez", 33);
        Estudiante[3] = ("cata", 27);
        Estudiante[4] = ("anawi", 12);

        for(Alumno a:Estudiante){
            System.out.println("Datos del estudiante"+a.getNombre()+a.getEdad())
        }
    }
}

```

## Colecciones y generics

Permite almacenar información de acuerdo a la necesidad.

Hay diferentes elementos que es Collection, List, Set, ArrayList, LinkedList, HashSet, TreeSet, **Se usa usando el por medio del paquete java.util**

### ArrayList

permite dinamizar los datos de un array y gestionar sus posiciones a traves de posiciones específicas.

La inserción de los datos se da de acuerdo a su orden de inserción.

```Java
import java.util.ArrayList;

public Class colecciones{

    public static void main(String[] args){

    
    //Creamos un array dinámico
    ArrayList nuevoArray = new ArrayList();

    //Llena el array con datos numéricos.
    nuevoArray.add(1);
    nuevoArray.add(2);
    nuevoArray.add(3);
    nuevoArray.add(4);
    nuevoArray.add(5);

    System.out.Println("Valores del array"+nuevoArray);
    
    //Llena el array con datos de tipo string
    ArrayList nuevoArrayString = new ArrayList();

    nuevoArrayString.add("hello");
    nuevoArrayString.add("world");
    nuevoArrayString.add("Alejandro");
    nuevoArrayString.add("ceron");

    System.out.Println("Valores del array"+nuevoArrayString);
}
}

```

### ArrayLinkedList

con array LinkedList conocemos cual es primer y último elemento de la lista.

```java
public Class coleccion{
    public static void main(String[] args){

        LinkedList arrayConocer = new LinkeList();

        arrayConocer.add(1);
        arrayConocer.add(2);
        arrayConocer.add(3;
        arrayConocer.add(4);

        //Agregamos el elemento 5 a la primera posición del arreglo.
        arrayConocer.addFirst(5);
        System.out.Println("Valores del array"+arrayConocer);

        //Obtiene y elemina el primer elemento del array
        arrayConocer.pool();
        System.out.Println("Array modificado"+arrayConocer);
    }
}
```

### HashSet

Con HashSet podemos establecer el orden del array bajo nuestro criterio por medio de clave o identificador del array, ejemplo:

Esta clase no permite elementos duplicados.

```java
public Class coleccion{
    //Creamos el objeto hastSet de tipo ARREGLO
    HastSet listaNumeros = new HastSet();

    listaNumeros.add(1);
    listaNumeros.add(2);
    listaNumeros.add(3);
    listaNumeros.add(4);

    System.out.println("Elementos del array "+listaNumeros);

    //Elimina un elemento especifico del array.

    //Aca decimos que borramos el array identificado con el valor de 3.
    listaNumeros.remove(3);

    //Mostramos en pantalla los cambios.
    System.out.println("Elementos del array borrados con el método remove "+listaNumeros);

}

```

### Treeset

Sirve para mostrar los datos de un elemento mayores o iguales al elemento enviado, por ejemplo, si le indicamos un valor de 3, entonces me muestra los elementos mayores o iguales a 3.

Mantiene siempre los elementos de manera ordenada, no permite elementos duplicados.

```Java
public Class mayorAItem{
    public static void main(string[] args){
        TreeSet itemsMayores = new TreeSet();
        itemsMayores.add(4);
        itemsMayores.add(8);
        itemsMayores.add(12);
        itemsMayores.add(2);
        itemsMayores.add(0);
        
        //Muestra los elementos mayores o iguales al elemento enviado como parámetro.
        System.out.println("elementos mayores a n elemento",itemsMayores.tailSet(4)); //Su salida en pantalla es un array con los elementos: 4,8,12
        //Muestra elementos en orden descendente
        System.out.println("elementos descendentes",itemsMayores.descendingSet()); // Muestra en pantalla 12,8,4,2,0
    }
}


```

### Generics y colecciones

Lo que hace colecciones es almacenar datos en un arreglo independientemente de su tipo pero a la larga a la hora de compilar o usar los datos nos marca un error porque estos datos no se almacenan de tipo string, float, int, entre otros, Sino que se almacenan de tipo object.

Para mejorar esto usamos Generics que es practicamente definir desde el array que vamos a definir y crear el tipo de elementos que vamos a recibir, así, si agregamos un elemento de diferente tipo, nos va a marcar un error.

```Java
public class generics{
    public static void main(string[]args){
        ArrayList <Integer> arrayExclusivoNum = new ArrayList();
        
        arrayExclusivoNum[1] = 4;
        arrayExclusivoNum[2] = 3;
        arrayExclusivoNum[3] = 10;
        arrayExclusivoNum[4] = "Hello world"; //En el editor nos marca un error porque estamos agregando datos de otro tipo al array de tipo Integer.
    }
}

```

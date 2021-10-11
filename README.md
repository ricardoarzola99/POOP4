//*PRINCIPAL
package POOP4;
public class POOP4 {
    public static void main(String[] args) {
System.out.println("-----Punto----");
Punto p1=new Punto();//Hace referencia a la clase, es un constructor vacìo
p1.imprimePunto();
p1.x=9;
p1.y=6;
p1.imprimePunto();
Punto p2=new Punto(33,88);
p2.imprimePunto();
    System.out.println("-----Perro----");
    //Imprimiendo valores de datos por medio de override
        System.out.println("Con override");
    Perro perro1=new Perro("Doggie","Pastor alemán","Abigail López","negro con dorado",2,true,true);
        System.out.println(perro1);
        perro1.doctor(5);
        perro1.jugar("parque");
        perro1.ladrar();
        perro1.juguete("pelota");
        perro1.recorrido(50);
        //Impresión de variables sin override
        System.out.println("Sin override");
    perro1.nombre="Douglas";
    perro1.imprimePerro();
    perro1.color="negro";
    perro1.imprime1();
        System.out.println("-----Estudiante----");
     Estudiante estudiante1=new Estudiante("Ricardo","Arzola",317134331,21,"5to");
     System.out.println(estudiante1);
     estudiante1.despertar();
     estudiante1.irAClase(3);
     estudiante1.hacerTarea(2);
     estudiante1.tratarDeDormir(30);
     estudiante1.estudiar();
     Estudiante estudiante2=new Estudiante("Julieta","Ramirez",317134332,22,"6to");
        System.out.println(estudiante2);
        System.out.println("-----Carro----");
        Carro carro1=new Carro("Honda","CR-V","Azul",2020,15000,false);
        System.out.println(carro1);
        carro1.servicio();
        carro1.gas(50);
        carro1.lugar("CU");
    carro1.vender("Roberto Arzola");
    carro1.recorrido((float) 60.6);
    Carro carro2=new Carro();
    carro2.km=60_000;
    carro2.servicio();
    System.out.println("-----Profesor----");
    Profesor profesor1=new Profesor("José Antonio","POO",8,5,"Ingenieria");
        System.out.println(profesor1);
        profesor1.estudiar();
        profesor1.aprobar();
        profesor1.horas(10);
        profesor1.tarea(12);
        profesor1.irAClase(4);
 }   
}
//*CLASE PERRO
package POOP4;
public class Perro {
  String nombre;
String raza;
String amo;
String color;
int edad;
boolean ladra;
boolean comer;  
    public Perro() {
    }
    public Perro(String nombre, String raza, String amo, String color, int edad, boolean ladra, boolean comer) {
        this.nombre = nombre;
        this.raza = raza;
        this.amo = amo;
        this.color = color;
        this.edad = edad;
        this.ladra = ladra;
        this.comer = comer;
    }
        public void jugar(String tipo){
        System.out.println("Al perro le gusta salir al "+tipo+" para jugar con los otros perros");  
    }
    public void juguete(String jugar){
        System.out.println("El perro siempre juega con su "+jugar+" con su amo");
    }
    public void ladrar(){
      if(ladra==true){
          System.out.println("El perro siempre ladra");   
      } else{
          System.out.println("El perro casi nunca ladra");    
      }}
    public void doctor(int mes){
        System.out.println("El perro va cada "+mes+" meses al doctor");
    }
    public void recorrido(float tiempo){
        System.out.println("El perro acostumbra a salir: "+tiempo+" minutos con su amo "+amo+" a correr");   
    }
    @Override
    public String toString() {
        return "Perro{" + "nombre=" + nombre + ", raza=" + raza + ", amo=" + amo + ", color=" + color + ", edad=" + edad + ", ladra=" + ladra + ", comer=" + comer + '}';
    }}
//*CLASE CARRO
package POOP4;
public class Carro {
String modelo;
String marca;
String color;
int año;
int km;
boolean std;

    public Carro() {
    }
    public Carro(String marca,String modelo, String color, int año, int km, boolean std) {
        this.modelo=modelo;
        this.marca = marca;
        this.color = color;
        this.año = año;
        this.km = km;
        this.std = std;
    }
    public void lugar(String lugar){
        System.out.println("Estoy yendo a "+lugar);  
    }
    public void vender(String comprador){
        System.out.println("Vendí mi coche a "+comprador);
    }
    public void gas(int gas){
        System.out.println("El carro tiene "+gas+" % de gasolina");  
    }
    public void servicio(){
        if(km>50000){
            System.out.println("El carro necesita servicio");    
        }else{
            System.out.println("Aún falta para ir al servicio, no te preocupes"); 
        }
    }
    public void recorrido(float tiempo){
        System.out.println("El tiempo de trayecto es: "+tiempo+" minutos");   
    }
//Para que imprima en pantalla los datos ingresados por el usuario
    @Override
    public String toString() {
        return "Carro{" + "marca=" + marca + ", modelo=" + modelo + ", color=" + color + ", año=" + año + ", km=" + km + ", std=" + std + '}';
    }
}
//*CLASE PUNTO
package POOP4;
public class Punto {
 //Sección de atributos
    int x,y;
 //Sección de constructores
 //Se necesitan dos constructores, uno para incicializar los valores en cero y otro para que reciba los valores
    public Punto() {//Constructor vacío, no recibe ningún parámetro, de no hacerlo, marcaría error en la classe principal
    }
    public Punto(int x, int y) {
        this.x = x;
        this.y = y;
        }
    public void imprimePunto() { 
        System.out.println("Punto [x="+x+" y="+y+"]");
    }   
    @Override
    public String toString() {
        return "Punto{" + "x=" + x + ", y=" + y + '}';
    }
}

//*CLASE ESTUDIANTE
package POOP4;
public class Estudiante{
String nombre;
String apellido;
int numCuenta;
int edad;
String grado;
public Estudiante(){
}
//@overload
public Estudiante(String nombre, String apellido,int numCuenta, int edad,String grado) {
   this.nombre=nombre;
  this.apellido=apellido;
  this.numCuenta=numCuenta;
   this.edad=edad;
   this.grado=grado;
} 
   public void estudiar(){
       System.out.println("Soy el estudiante "+nombre+" y estoy estudiando");
}
   public void tratarDeDormir(int minutos){
       System.out.println("Voy a tratar de dormir "+minutos+" minutos");
}
   public void hacerTarea(int cantidadDeTareas){
       System.out.println("Voy a hacer "+cantidadDeTareas+" tareas");
}
   public void despertar(){
       System.out.println("Estoy despertando");   
   }
   public void irAClase(int numMaterias){
       System.out.println("Estoy en "+grado+" grado y tengo "+numMaterias+" materias");
}  
    @Override
    public String toString() {
        return "Estudiante{" + "nombre=" + nombre + ", apellido=" + apellido + ", numCuenta=" + numCuenta + ", edad=" + edad + ", grado=" + grado + '}';
    }
}
//*CLASE PROFESOR
package POOP4;
public class Profesor {
String nombre;
String materia;
int excentar;
int grupos;
String grado;
    public Profesor(){
 }
 //@overload
    public Profesor(String nombre, String materia, int excentar, int grupos, String grado) {
        this.nombre = nombre;
        this.materia = materia;
        this.excentar = excentar;
        this.grupos = grupos;
        this.grado = grado;
    }
   public void estudiar(){
       System.out.println("El estudiante necesita estudiar mucho la materia del profesor "+nombre+" para poder aprobar");
}
   public void horas(int hr){
       System.out.println("El profesor "+nombre+" imparte "+hr+" horas a la semana");
}
   public void tarea(int cantidadDeTareas){
       System.out.println("Voy a hacer "+cantidadDeTareas+" tareas para poder excentar");
}
   public void aprobar(){
        if(excentar>7){
            System.out.println("El alumno ha excentado");    
        }else{
            System.out.println("El alumno está en examen final"); 
        }
    }
   public void irAClase(int numMaterias){
       System.out.println("El profesor imparte "+numMaterias+" materias a la semana porque estudió una "+grado);
}
    @Override
    public String toString() {
        return "PROFESOR{" + "nombre=" + nombre + ", materia=" + materia + ", excentar=" + excentar + ", grupos=" + grupos + ", grado=" + grado + '}';
    } 
}


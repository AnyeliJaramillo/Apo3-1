```
package umariana.taller1;


import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
import mundo.Tarea;

/**
 * 
 * @author Anyeli Jaramillo
 */

public class Taller1 {

    public static void main(String[] args) {
        System.out.println("BIENVENIDO AL PROGRAMA DE LISTADO EN ORDEN ");
    
    Scanner lector=new Scanner(System.in);
    boolean activo= true;
    boolean tareaAgregada=false;

    //se crea un array para poder agregar datos en tarea 
    ArrayList<Tarea> misTareas=new ArrayList<>();

    
    do{
        // Menu de opciones 
            System.out.println("=== MENU DE OPCIONES ==="); 
            System.out.println( "1.Agregar tarea"); 
            System.out.println( "2.Mostrar tarea"); 
            System.out.println( "3.Lista de pendientes"); 
            System.out.println( "4.Teminar programa"); 
            int opcion = lector.nextInt();
            
            // Evalua los casos 
            switch(opcion){
                
                case 1 -> {
                    System.out.println("====AGREGAR TAREA====");
                    System.out.println("Ingrese el id de la tarea");
                     // lee
                    int idTarea = lector.nextInt();

                    lector.nextLine();
                    System.out.println("Ingrese la descripcion de la tarea");
                    String descripcion = lector.nextLine();

                    int prioridad;
                    // mientras se cumpla la condicion 
                    do {
                        System.out.println("Ingrese la prioridad de la tarea del 1-5");
                        prioridad = lector.nextInt();
                        
                        // Establece el rango de la prioridad
                        if (prioridad < 1 || prioridad > 5) {
                            System.out.println("La prioridad debe estar entre 1 a 5. Inténtelo otra vez.");
                        }else{
                            
                        }
                    } while (prioridad < 1 || prioridad > 5);
                     // Creacion del objeto y llenar la informacion
                    Tarea nuevaTarea = new Tarea(idTarea, descripcion, prioridad);
                    // Almacenar el objeto en la contenedora
                    misTareas.add(nuevaTarea);
                    System.out.println(" Su tarea fue agregada Satisfactoriamente");
                    tareaAgregada=true;
                }
                  
                    
                case 2 -> {
                    // Cuando no agregan tareas
                    if(tareaAgregada==false){
                        System.out.println("No has ingresado tareas\n agrega una :)");
                    }else{
                        System.out.println("====TAREAS REGISTRADAS====");
                        for(Tarea t: misTareas){
                            System.out.println("Id: "+t.getIdTarea());
                            System.out.println("Descripcion: "+t.getDescripcion());
                            System.out.println("Prioridad: "+t.getPrioridad());
                            System.out.println("==================");
                        }  
                    }
                }
                case 3 -> { 
                    if(tareaAgregada==false){
                        System.out.println("No has ingresado tareas\n agrega una :) ");
                    }else{
                        System.out.println("==== LAS  TAREAS AGREGADAS Y SU PRIORIDAD====");
    
                        // Con i= 5  inicializacion 
                        // Con i >=1 condicion 
                        // Con i --  decrecimiento
                         for (int i = 5; i >= 1; i--) {        
                            for (Tarea tarea : misTareas) {
                                if (tarea.getPrioridad() == i) {
                                    // Mostramos 
                                    System.out.println("Id: " + tarea.getIdTarea());
                                    System.out.println("Descripción: " + tarea.getDescripcion());
                                    System.out.println("Prioridad: " + tarea.getPrioridad());
                                }
                            }
                        }
                    }

                    }
                
                case 4 -> {
                    System.out.println("ADIOS has salido del programa");
                    activo=false;
                }
                // No cumple ninguna condicion 
                default -> System.out.println("Opcioon incorrecta, ingresa una opcion valida");
            }
}while(activo);
    
}
}
```

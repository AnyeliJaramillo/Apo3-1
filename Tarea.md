```
package mundo;

/**
 *
 * @author Anyeli Jaramillo
 */
public class Tarea {
    // atributos
    private int idTarea;
    private String descricion;
    private int prioridad;
    // metodos

    public Tarea() {
        
        
    }

    public Tarea(int idTarea, String descricion, int prioridad) {
        this.idTarea = idTarea;
        this.descricion = descricion;
        this.prioridad = prioridad;
    }

    //Constructores get y set
    
    public int getIdTarea() {
        return idTarea;
    }

    public void setIdTarea(int idTarea) {
        this.idTarea = idTarea;
    }

    public String getDescripcion() {
        return descricion;
    }

    public void setDescricion(String descricion) {
        this.descricion = descricion;
    }

    public int getPrioridad() {
        return prioridad;
    }

    public void setPrioridad(int prioridad) {
        this.prioridad = prioridad;
    }
    
    
    
}
```

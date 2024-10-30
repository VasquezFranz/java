
public class Alumno {
    private String foto;
    private String nombre;
    private int edad;
    private int practica1;
    private int practica2;
    private int practica3;
    private int examenFinal;

    // Constructor parametrizado
    public Alumno(String foto, String nombre, int edad, int practica1, int practica2, int practica3, int examenFinal) {
        this.foto = foto;
        this.nombre = nombre;
        this.edad = edad;
        this.practica1 = practica1;
        this.practica2 = practica2;
        this.practica3 = practica3;
        this.examenFinal = examenFinal;
    }

    // Getters y Setters
    public String getFoto() {
        return foto;
    }

    public void setFoto(String foto) {
        this.foto = foto;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public int getEdad() {
        return edad;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }

    public int getPractica1() {
        return practica1;
    }

    public void setPractica1(int practica1) {
        this.practica1 = practica1;
    }

    public int getPractica2() {
        return practica2;
    }

    public void setPractica2(int practica2) {
        this.practica2 = practica2;
    }

    public int getPractica3() {
        return practica3;
    }

    public void setPractica3(int practica3) {
        this.practica3 = practica3;
    }

    public int getExamenFinal() {
        return examenFinal;
    }

    public void setExamenFinal(int examenFinal) {
        this.examenFinal = examenFinal;
    }

    @Override
    public String toString() {
        return "Alumno{" +
                "foto='" + foto + '\'' +
                ", nombre='" + nombre + '\'' +
                ", edad=" + edad +
                ", practica1=" + practica1 +
                ", practica2=" + practica2 +
                ", practica3=" + practica3 +
                ", examenFinal=" + examenFinal +
                '}';
    }
}

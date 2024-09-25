# java
import java.util.Scanner;
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class EmpleadoInfo {
    private static String nombre;
    private static String apellidos;
    private static double sueldoMensual;

    private static final Pattern NOMBRE_APELLIDO_PATTERN = Pattern.compile("^[A-Za-záéíóúÁÉÍÓÚñÑ]+( [A-Za-záéíóúÁÉÍÓÚñÑ]+)*$");

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int opcion;

        do {
            System.out.println("Menu:");
            System.out.println("1. Ingresar nombre y apellidos del empleado");
            System.out.println("2. Ingresar sueldo mensual del empleado");
            System.out.println("3. Elaborar reporte ASCII");
            System.out.println("0. Salir");
            System.out.print("Seleccione una opción: ");
            opcion = scanner.nextInt();
            scanner.nextLine(); // Consumir el salto de línea

            switch (opcion) {
                case 1:
                    ingresarNombreApellidos(scanner);
                    break;
                case 2:
                    ingresarSueldo(scanner);
                    break;
                case 3:
                    elaborarReporte();
                    break;
                case 0:
                    System.out.println("Saliendo...");
                    break;
                default:
                    System.out.println("Opción inválida. Intente nuevamente.");
            }
        } while (opcion != 0);

        scanner.close();
    }

    private static void ingresarNombreApellidos(Scanner scanner) {
        System.out.print("Ingrese el nombre del empleado: ");
        String nombreInput = scanner.nextLine();
        System.out.print("Ingrese los apellidos del empleado: ");
        String apellidosInput = scanner.nextLine();

        if (validarNombreApellidos(nombreInput) && validarNombreApellidos(apellidosInput)) {
            nombre = nombreInput;
            apellidos = apellidosInput;
            System.out.println("Nombre y apellidos ingresados correctamente.");
        } else {
            System.out.println("Nombre o apellidos no válidos. Deben contener solo letras.");
        }
    }

    private static void ingresarSueldo(Scanner scanner) {
        System.out.print("Ingrese el sueldo mensual del empleado: ");
        double sueldoInput = scanner.nextDouble();

        if (sueldoInput >= 0) {
            sueldoMensual = sueldoInput;
            System.out.println("Sueldo ingresado correctamente.");
        } else {
            System.out.println("El sueldo debe ser un valor positivo.");
        }
    }

    private static void elaborarReporte() {
        if (nombre != null && apellidos != null && sueldoMensual > 0) {
            System.out.println("----- Reporte del Empleado -----");
            System.out.println("Nombre: " + nombre);
            System.out.println("Apellidos: " + apellidos);
            System.out.println("Sueldo Mensual: $" + sueldoMensual);
        } else {
            System.out.println("Debe ingresar primero el nombre, apellidos y sueldo del empleado.");
        }
    }

    private static boolean validarNombreApellidos(String input) {
        Matcher matcher = NOMBRE_APELLIDO_PATTERN.matcher(input);
        return matcher.matches();
    }
}

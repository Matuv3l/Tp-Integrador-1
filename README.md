# Tp-Integrador-1

1. Clase Utiles - Validaciones
import java.util.InputMismatchException;
import java.util.Scanner;

public class Utiles {
    
    public static int verificarEntero(Scanner scanner, String mensaje) {
        int valor = 0;
        boolean valido = false;
        do {
            try {
                System.out.print(mensaje);
                valor = scanner.nextInt();
                valido = true;
            } catch (InputMismatchException e) {
                System.out.println("Error: Debe ingresar un número entero válido.");
                scanner.next(); // Limpiar el buffer
            }
        } while (!valido);
        return valor;
    }
    
    public static double verificarDouble(Scanner scanner, String mensaje) {
        double valor = 0;
        boolean valido = false;
        do {
            try {
                System.out.print(mensaje);
                valor = scanner.nextDouble();
                valido = true;
            } catch (InputMismatchException e) {
                System.out.println("Error: Debe ingresar un número decimal válido.");
                scanner.next();
            }
        } while (!valido);
        return valor;
    }
    
    public static String verificarString(Scanner scanner, String mensaje) {
        System.out.print(mensaje);
        return scanner.next();
    }
    
    public static int verificarEnteroPositivo(Scanner scanner, String mensaje) {
        int valor;
        do {
            valor = verificarEntero(scanner, mensaje);
            if (valor <= 0) {
                System.out.println("Error: Debe ingresar un número positivo.");
            }
        } while (valor <= 0);
        return valor;
    }
    
    public static double verificarDoublePositivo(Scanner scanner, String mensaje) {
        double valor;
        do {
            valor = verificarDouble(scanner, mensaje);
            if (valor <= 0) {
                System.out.println("Error: Debe ingresar un número positivo.");
            }
        } while (valor <= 0);
        return valor;
    }
}
2. Clase Programa
java
public class Programa {
    private String nombre;
    private int hilosProcesador;
    private double frecuenciaProcesador; // en GHz
    private int ramRequerida; // en GB
    private int vramRequerida; // en GB
    private int almacenamientoRequerido; // en GB
    
    public Programa() {
    }
    
    public Programa(String nombre, int hilosProcesador, double frecuenciaProcesador, 
                    int ramRequerida, int vramRequerida, int almacenamientoRequerido) {
        this.nombre = nombre;
        this.hilosProcesador = hilosProcesador;
        this.frecuenciaProcesador = frecuenciaProcesador;
        this.ramRequerida = ramRequerida;
        this.vramRequerida = vramRequerida;
        this.almacenamientoRequerido = almacenamientoRequerido;
    }
    
    // Getters y Setters
    public String getNombre() {
        return nombre;
    }
    
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    public int getHilosProcesador() {
        return hilosProcesador;
    }
    
    public void setHilosProcesador(int hilosProcesador) {
        this.hilosProcesador = hilosProcesador;
    }
    
    public double getFrecuenciaProcesador() {
        return frecuenciaProcesador;
    }
    
    public void setFrecuenciaProcesador(double frecuenciaProcesador) {
        this.frecuenciaProcesador = frecuenciaProcesador;
    }
    
    public int getRamRequerida() {
        return ramRequerida;
    }
    
    public void setRamRequerida(int ramRequerida) {
        this.ramRequerida = ramRequerida;
    }
    
    public int getVramRequerida() {
        return vramRequerida;
    }
    
    public void setVramRequerida(int vramRequerida) {
        this.vramRequerida = vramRequerida;
    }
    
    public int getAlmacenamientoRequerido() {
        return almacenamientoRequerido;
    }
    
    public void setAlmacenamientoRequerido(int almacenamientoRequerido) {
        this.almacenamientoRequerido = almacenamientoRequerido;
    }
    
    public void mostrarPrograma() {
        System.out.println("Programa: " + nombre);
        System.out.println("  - Hilos de procesador: " + hilosProcesador);
        System.out.println("  - Frecuencia de procesador: " + frecuenciaProcesador + " GHz");
        System.out.println("  - RAM requerida: " + ramRequerida + " GB");
        System.out.println("  - VRAM requerida: " + vramRequerida + " GB");
        System.out.println("  - Almacenamiento requerido: " + almacenamientoRequerido + " GB");
    }
}
3. Clase Computadora
java
public class Computadora {
    private String marca;
    private String modelo;
    private String nombreProcesador;
    private int hilosProcesador;
    private double frecuenciaProcesador; // en GHz
    private int ram; // en GB
    private String nombrePlacaVideo;
    private String modeloPlacaVideo;
    private int vram; // en GB
    private int almacenamiento; // en GB
    private double precio;
    private double ganancia;
    
    public Computadora() {
    }
    
    public Computadora(String marca, String modelo, String nombreProcesador, int hilosProcesador,
                       double frecuenciaProcesador, int ram, String nombrePlacaVideo,
                       String modeloPlacaVideo, int vram, int almacenamiento, 
                       double precio, double ganancia) {
        this.marca = marca;
        this.modelo = modelo;
        this.nombreProcesador = nombreProcesador;
        this.hilosProcesador = hilosProcesador;
        this.frecuenciaProcesador = frecuenciaProcesador;
        this.ram = ram;
        this.nombrePlacaVideo = nombrePlacaVideo;
        this.modeloPlacaVideo = modeloPlacaVideo;
        this.vram = vram;
        this.almacenamiento = almacenamiento;
        this.precio = precio;
        this.ganancia = ganancia;
    }
    
    // Getters y Setters
    public String getMarca() {
        return marca;
    }
    
    public void setMarca(String marca) {
        this.marca = marca;
    }
    
    public String getModelo() {
        return modelo;
    }
    
    public void setModelo(String modelo) {
        this.modelo = modelo;
    }
    
    public String getNombreProcesador() {
        return nombreProcesador;
    }
    
    public void setNombreProcesador(String nombreProcesador) {
        this.nombreProcesador = nombreProcesador;
    }
    
    public int getHilosProcesador() {
        return hilosProcesador;
    }
    
    public void setHilosProcesador(int hilosProcesador) {
        this.hilosProcesador = hilosProcesador;
    }
    
    public double getFrecuenciaProcesador() {
        return frecuenciaProcesador;
    }
    
    public void setFrecuenciaProcesador(double frecuenciaProcesador) {
        this.frecuenciaProcesador = frecuenciaProcesador;
    }
    
    public int getRam() {
        return ram;
    }
    
    public void setRam(int ram) {
        this.ram = ram;
    }
    
    public String getNombrePlacaVideo() {
        return nombrePlacaVideo;
    }
    
    public void setNombrePlacaVideo(String nombrePlacaVideo) {
        this.nombrePlacaVideo = nombrePlacaVideo;
    }
    
    public String getModeloPlacaVideo() {
        return modeloPlacaVideo;
    }
    
    public void setModeloPlacaVideo(String modeloPlacaVideo) {
        this.modeloPlacaVideo = modeloPlacaVideo;
    }
    
    public int getVram() {
        return vram;
    }
    
    public void setVram(int vram) {
        this.vram = vram;
    }
    
    public int getAlmacenamiento() {
        return almacenamiento;
    }
    
    public void setAlmacenamiento(int almacenamiento) {
        this.almacenamiento = almacenamiento;
    }
    
    public double getPrecio() {
        return precio;
    }
    
    public void setPrecio(double precio) {
        this.precio = precio;
    }
    
    public double getGanancia() {
        return ganancia;
    }
    
    public void setGanancia(double ganancia) {
        this.ganancia = ganancia;
    }
    
    public void mostrarComputadora() {
        System.out.println("--- " + marca + " " + modelo + " ---");
        System.out.println("Procesador: " + nombreProcesador + " (" + hilosProcesador + " hilos, " + frecuenciaProcesador + " GHz)");
        System.out.println("RAM: " + ram + " GB");
        System.out.println("Placa de video: " + nombrePlacaVideo + " " + modeloPlacaVideo + " (" + vram + " GB VRAM)");
        System.out.println("Almacenamiento: " + almacenamiento + " GB");
        System.out.println("Precio: $" + precio);
        System.out.println("Ganancia: $" + ganancia);
        System.out.println();
    }
}
4. Clase Tienda - Lógica del negocio
java
import java.util.Scanner;

public class Tienda {
    private Computadora[] computadoras;
    private Programa[] programasDisponibles;
    private Scanner scanner;
    
    public Tienda() {
        scanner = new Scanner(System.in);
        inicializarComputadoras();
        inicializarProgramas();
    }
    
    private void inicializarComputadoras() {
        computadoras = new Computadora[6];
        
        computadoras[0] = new Computadora("HP", "Pavilion 15", "Intel Core i3", 4, 2.4, 8, 
                                           "Intel", "UHD Graphics", 2, 256, 45000, 5000);
        computadoras[1] = new Computadora("Lenovo", "ThinkPad X1", "Intel Core i5", 8, 3.0, 16,
                                           "Intel", "Iris Xe", 4, 512, 85000, 8000);
        computadoras[2] = new Computadora("Dell", "Inspiron 14", "AMD Ryzen 5", 12, 3.2, 16,
                                           "AMD", "Radeon Graphics", 4, 512, 72000, 6500);
        computadoras[3] = new Computadora("Asus", "ROG Strix", "Intel Core i7", 16, 3.8, 32,
                                           "NVIDIA", "RTX 3060", 8, 1024, 150000, 20000);
        computadoras[4] = new Computadora("Acer", "Nitro 5", "AMD Ryzen 7", 16, 3.6, 24,
                                           "NVIDIA", "GTX 1660 Ti", 6, 512, 110000, 12000);
        computadoras[5] = new Computadora("MacBook", "Pro M3", "Apple M3", 12, 3.5, 18,
                                           "Apple", "M3 GPU", 8, 512, 180000, 25000);
    }
    
    private void inicializarProgramas() {
        programasDisponibles = new Programa[6];
        
        programasDisponibles[0] = new Programa("Microsoft Word", 2, 1.5, 4, 1, 10);
        programasDisponibles[1] = new Programa("Photoshop", 4, 2.0, 8, 2, 20);
        programasDisponibles[2] = new Programa("AutoCAD", 8, 2.5, 16, 4, 30);
        programasDisponibles[3] = new Programa("Premiere Pro", 8, 3.0, 16, 4, 50);
        programasDisponibles[4] = new Programa("Minecraft", 4, 2.0, 8, 2, 5);
        programasDisponibles[5] = new Programa("Cyberpunk 2077", 12, 3.2, 16, 8, 70);
    }
    
    public void mostrarMenu() {
        int opcion;
        do {
            System.out.println("\n===== TIENDA DE COMPUTACIÓN =====");
            System.out.println("1) Computadora más económica");
            System.out.println("2) Computadora más cara");
            System.out.println("3) Elegir computador");
            System.out.println("4) Computadora según necesidades del cliente");
            System.out.println("5) Mostrar programas que pueda correr una computadora");
            System.out.println("6) Salir");
            System.out.print("Seleccione una opción: ");
            
            opcion = Utiles.verificarEntero(scanner, "");
            
            switch (opcion) {
                case 1:
                    computadoraMasEconomica();
                    break;
                case 2:
                    computadoraMasCara();
                    break;
                case 3:
                    elegirComputador();
                    break;
                case 4:
                    computadoraSegunNecesidades();
                    break;
                case 5:
                    mostrarProgramasCompatibles();
                    break;
                case 6:
                    System.out.println("¡Gracias por visitar la tienda!");
                    break;
                default:
                    System.out.println("Opción no válida, intente de nuevo.");
            }
        } while (opcion != 6);
    }
    
    // Opción 1: Computadora más económica
    private void computadoraMasEconomica() {
        if (computadoras.length == 0) {
            System.out.println("No hay computadoras disponibles.");
            return;
        }
        
        Computadora masBarata = computadoras[0];
        for (int i = 1; i < computadoras.length; i++) {
            if (computadoras[i].getPrecio() < masBarata.getPrecio()) {
                masBarata = computadoras[i];
            }
        }
        
        System.out.println("\n=== COMPUTADORA MÁS ECONÓMICA ===");
        masBarata.mostrarComputadora();
    }
    
    // Opción 2: Computadora más cara
    private void computadoraMasCara() {
        if (computadoras.length == 0) {
            System.out.println("No hay computadoras disponibles.");
            return;
        }
        
        Computadora masCara = computadoras[0];
        for (int i = 1; i < computadoras.length; i++) {
            if (computadoras[i].getPrecio() > masCara.getPrecio()) {
                masCara = computadoras[i];
            }
        }
        
        System.out.println("\n=== COMPUTADORA MÁS CARA ===");
        masCara.mostrarComputadora();
    }
    
    // Opción 3: Elegir computador y mostrar submenú
    private void elegirComputador() {
        if (computadoras.length == 0) {
            System.out.println("No hay computadoras disponibles.");
            return;
        }
        
        System.out.println("\n=== COMPUTADORAS DISPONIBLES ===");
        for (int i = 0; i < computadoras.length; i++) {
            System.out.println((i + 1) + ") " + computadoras[i].getMarca() + " " + computadoras[i].getModelo() + " - $" + computadoras[i].getPrecio());
        }
        
        System.out.print("\nSeleccione una computadora (1-" + computadoras.length + "): ");
        int seleccion = Utiles.verificarEntero(scanner, "");
        
        if (seleccion < 1 || seleccion > computadoras.length) {
            System.out.println("Selección no válida.");
            return;
        }
        
        Computadora elegida = computadoras[seleccion - 1];
        System.out.println("\n=== COMPUTADORA SELECCIONADA ===");
        elegida.mostrarComputadora();
        
        // Submenú de opciones para la computadora seleccionada
        mostrarSubMenuComputadora(elegida);
    }
    
    // Submenú que se muestra después de elegir una computadora
    private void mostrarSubMenuComputadora(Computadora pc) {
        int opcion;
        do {
            System.out.println("\n--- Opciones para " + pc.getMarca() + " " + pc.getModelo() + " ---");
            System.out.println("1) Mostrar datos completos");
            System.out.println("2) Mostrar programas que puede ejecutar");
            System.out.println("3) Volver al menú principal");
            System.out.print("Seleccione una opción: ");
            
            opcion = Utiles.verificarEntero(scanner, "");
            
            switch (opcion) {
                case 1:
                    pc.mostrarComputadora();
                    break;
                case 2:
                    programasCompatiblesDeUnaPc(pc);
                    break;
                case 3:
                    System.out.println("Volviendo al menú principal...");
                    break;
                default:
                    System.out.println("Opción no válida.");
            }
        } while (opcion != 3);
    }
    
    // Opción 4: Computadora según necesidades del cliente
    private void computadoraSegunNecesidades() {
        System.out.println("\n=== COMPUTADORA SEGÚN NECESIDADES ===");
        
        // Cargar programas deseados
        Programa[] programasDeseados = cargarProgramasDeseados();
        
        if (programasDeseados.length == 0) {
            System.out.println("No se cargaron programas.");
            return;
        }
        
        // Calcular requisitos máximos
        int[] requisitosMaximos = calcularRequisitosMaximos(programasDeseados);
        
        System.out.println("\n--- Requisitos mínimos necesarios ---");
        System.out.println("Hilos de procesador: " + requisitosMaximos[0]);
        System.out.println("Frecuencia de procesador: " + requisitosMaximos[1] + " GHz");
        System.out.println("RAM: " + requisitosMaximos[2] + " GB");
        System.out.println("VRAM: " + requisitosMaximos[3] + " GB");
        System.out.println("Almacenamiento: " + requisitosMaximos[4] + " GB");
        
        // Buscar computadoras compatibles
        Computadora[] compatibles = buscarComputadorasCompatibles(requisitosMaximos);
        
        if (compatibles.length == 0) {
            System.out.println("\nNo hay computadoras que cumplan con los requisitos.");
            return;
        }
        
        // Ordenar por ganancia de mayor a menor
        ordenarPorGanancia(compatibles);
        
        System.out.println("\n=== COMPUTADORAS RECOMENDADAS (ordenadas por ganancia) ===");
        for (int i = 0; i < compatibles.length; i++) {
            System.out.println("\n" + (i + 1) + ")");
            compatibles[i].mostrarComputadora();
        }
        
        // Preguntar si quiere cambiar alguna PC (personalizar)
        System.out.print("¿Desea elegir una de estas computadoras? (1: Sí / 0: No): ");
        int respuesta = Utiles.verificarEntero(scanner, "");
        
        if (respuesta == 1) {
            System.out.print("Seleccione el número de la computadora (1-" + compatibles.length + "): ");
            int seleccion = Utiles.verificarEntero(scanner, "");
            
            if (seleccion >= 1 && seleccion <= compatibles.length) {
                System.out.println("\n=== COMPUTADORA ELEGIDA ===");
                compatibles[seleccion - 1].mostrarComputadora();
                mostrarSubMenuComputadora(compatibles[seleccion - 1]);
            } else {
                System.out.println("Selección no válida.");
            }
        }
    }
    
    // Cargar programas que el cliente desea instalar
    private Programa[] cargarProgramasDeseados() {
        System.out.println("\n--- Programas disponibles ---");
        for (int i = 0; i < programasDisponibles.length; i++) {
            System.out.println((i + 1) + ") " + programasDisponibles[i].getNombre());
        }
        System.out.println("0) Terminar carga");
        
        // Primera pasada: contar cuántos programas selecciona
        int contador = 0;
        int[] indicesSeleccionados = new int[programasDisponibles.length];
        
        System.out.println("\nSeleccione los programas que desea instalar (ingrese el número):");
        int seleccion;
        do {
            seleccion = Utiles.verificarEntero(scanner, "Programa #" + (contador + 1) + ": ");
            
            if (seleccion > 0 && seleccion <= programasDisponibles.length) {
                boolean yaAgregado = false;
                for (int i = 0; i < contador; i++) {
                    if (indicesSeleccionados[i] == seleccion - 1) {
                        yaAgregado = true;
                        break;
                    }
                }
                if (!yaAgregado) {
                    indicesSeleccionados[contador] = seleccion - 1;
                    contador++;
                    System.out.println("  -> '" + programasDisponibles[seleccion - 1].getNombre() + "' agregado.");
                } else {
                    System.out.println("  Ese programa ya fue seleccionado.");
                }
            } else if (seleccion != 0) {
                System.out.println("Número no válido.");
            }
        } while (seleccion != 0);
        
        // Crear el array con los programas seleccionados
        Programa[] programasDeseados = new Programa[contador];
        for (int i = 0; i < contador; i++) {
            programasDeseados[i] = programasDisponibles[indicesSeleccionados[i]];
        }
        
        return programasDeseados;
    }
    
    // Calcular los requisitos máximos de todos los programas seleccionados
    private int[] calcularRequisitosMaximos(Programa[] programas) {
        int maxHilos = 0;
        double maxFrecuencia = 0;
        int maxRam = 0;
        int maxVram = 0;
        int maxAlmacenamiento = 0;
        
        for (int i = 0; i < programas.length; i++) {
            if (programas[i].getHilosProcesador() > maxHilos) {
                maxHilos = programas[i].getHilosProcesador();
            }
            if (programas[i].getFrecuenciaProcesador() > maxFrecuencia) {
                maxFrecuencia = programas[i].getFrecuenciaProcesador();
            }
            if (programas[i].getRamRequerida() > maxRam) {
                maxRam = programas[i].getRamRequerida();
            }
            if (programas[i].getVramRequerida() > maxVram) {
                maxVram = programas[i].getVramRequerida();
            }
            maxAlmacenamiento += programas[i].getAlmacenamientoRequerido();
        }
        
        return new int[]{maxHilos, (int) maxFrecuencia, maxRam, maxVram, maxAlmacenamiento};
    }
    
    // Buscar computadoras que cumplan con los requisitos
    private Computadora[] buscarComputadorasCompatibles(int[] requisitos) {
        // Primero contar cuántas cumplen
        int contador = 0;
        for (int i = 0; i < computadoras.length; i++) {
            if (computadoras[i].getHilosProcesador() >= requisitos[0] &&
                computadoras[i].getFrecuenciaProcesador() >= requisitos[1] &&
                computadoras[i].getRam() >= requisitos[2] &&
                computadoras[i].getVram() >= requisitos[3] &&
                computadoras[i].getAlmacenamiento() >= requisitos[4]) {
                contador++;
            }
        }
        
        // Crear array con las compatibles
        Computadora[] compatibles = new Computadora[contador];
        int index = 0;
        for (int i = 0; i < computadoras.length; i++) {
            if (computadoras[i].getHilosProcesador() >= requisitos[0] &&
                computadoras[i].getFrecuenciaProcesador() >= requisitos[1] &&
                computadoras[i].getRam() >= requisitos[2] &&
                computadoras[i].getVram() >= requisitos[3] &&
                computadoras[i].getAlmacenamiento() >= requisitos[4]) {
                compatibles[index] = computadoras[i];
                index++;
            }
        }
        
        return compatibles;
    }
    
    // Ordenar computadoras por ganancia de mayor a menor (Bubble Sort)
    private void ordenarPorGanancia(Computadora[] compatibles) {
        for (int i = 0; i < compatibles.length - 1; i++) {
            for (int j = 0; j < compatibles.length - 1 - i; j++) {
                if (compatibles[j].getGanancia() < compatibles[j + 1].getGanancia()) {
                    Computadora temp = compatibles[j];
                    compatibles[j] = compatibles[j + 1];
                    compatibles[j + 1] = temp;
                }
            }
        }
    }
    
    // Opción 5: Mostrar programas que pueda correr una computadora
    private void mostrarProgramasCompatibles() {
        System.out.println("\n=== PROGRAMAS COMPATIBLES CON UNA COMPUTADORA ===");
        
        // Mostrar lista de computadoras
        System.out.println("Seleccione una computadora:");
        for (int i = 0; i < computadoras.length; i++) {
            System.out.println((i + 1) + ") " + computadoras[i].getMarca() + " " + computadoras[i].getModelo());
        }
        
        System.out.print("\nIngrese el número de la computadora (1-" + computadoras.length + "): ");
        int seleccion = Utiles.verificarEntero(scanner, "");
        
        if (seleccion < 1 || seleccion > computadoras.length) {
            System.out.println("Selección no válida.");
            return;
        }
        
        Computadora pc = computadoras[seleccion - 1];
        System.out.println("\n=== COMPUTADORA SELECCIONADA ===");
        pc.mostrarComputadora();
        
        programasCompatiblesDeUnaPc(pc);
    }
    
    // Ver qué programas puede ejecutar una computadora específica
    private void programasCompatiblesDeUnaPc(Computadora pc) {
        System.out.println("\n--- Programas que puede ejecutar " + pc.getMarca() + " " + pc.getModelo() + " ---");
        
        int contador = 0;
        for (int i = 0; i < programasDisponibles.length; i++) {
            if (pc.getHilosProcesador() >= programasDisponibles[i].getHilosProcesador() &&
                pc.getFrecuenciaProcesador() >= programasDisponibles[i].getFrecuenciaProcesador() &&
                pc.getRam() >= programasDisponibles[i].getRamRequerida() &&
                pc.getVram() >= programasDisponibles[i].getVramRequerida() &&
                pc.getAlmacenamiento() >= programasDisponibles[i].getAlmacenamientoRequerido()) {
                
                System.out.println("\n✓ " + programasDisponibles[i].getNombre());
                contador++;
            }
        }
        
        if (contador == 0) {
            System.out.println("Esta computadora no puede ejecutar ninguno de los programas disponibles.");
        } else {
            System.out.println("\nTotal: " + contador + " programas compatibles.");
        }
    }
}
5. Clase Main
java
public class Main {
    public static void main(String[] args) {
        Tienda tienda = new Tienda();
        tienda.mostrarMenu();
    }
}

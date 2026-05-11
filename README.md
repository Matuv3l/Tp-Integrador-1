# Tp-Integrador-1
import java.util.Scanner;

class Computadora {
    String marca;
    String modelo;
    String procesador;
    int hilos;
    double frecuencia;
    int ram;
    int vram;
    int almacenamiento;
    int precio;
    int ganancia;

    public Computadora(String marca, String modelo, String procesador, int hilos, double frecuencia,
                       int ram, int vram, int almacenamiento, int precio, int ganancia) {
        this.marca = marca;
        this.modelo = modelo;
        this.procesador = procesador;
        this.hilos = hilos;
        this.frecuencia = frecuencia;
        this.ram = ram;
        this.vram = vram;
        this.almacenamiento = almacenamiento;
        this.precio = precio;
        this.ganancia = ganancia;
    }

    public String mostrar() {
        return marca + " " + modelo + " | Proc: " + procesador + " | RAM: " + ram + "GB | VRAM: " + vram +
                "GB | Almacenamiento: " + almacenamiento + "GB | Precio: $" + precio + " | Ganancia: $" + ganancia;
    }
}

class Programa {
    String nombre;
    int hilos;
    double frecuencia;
    int ram;
    int vram;
    int almacenamiento;

    public Programa(String nombre, int hilos, double frecuencia, int ram, int vram, int almacenamiento) {
        this.nombre = nombre;
        this.hilos = hilos;
        this.frecuencia = frecuencia;
        this.ram = ram;
        this.vram = vram;
        this.almacenamiento = almacenamiento;
    }

    public String mostrar() {
        return nombre + " | Hilos: " + hilos + " | Frec: " + frecuencia + "GHz | RAM: " + ram +
                "GB | VRAM: " + vram + "GB | Almacenamiento: " + almacenamiento + "GB";
    }
}

public class TiendaComputacion {
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        // Cargar algunos datos de ejemplo
        Computadora[] pcs = {
                new Computadora("Asus", "Zenbook UX330", "Athlon 3000G", 2, 3.5, 1, 1, 80, 20000, 3000),
                new Computadora("Apple", "IMac PRO", "Core i9-10980XE", 36, 3.0, 128, 48, 8000, 680000, 95000),
                new Computadora("Dell", "XPS 15", "Core DUO ULV U2500", 2, 1.2, 2, 3, 160, 11000, 1500)
        };

        Programa[] programas = {
                new Programa("Cyberpunk 2077", 8, 3.6, 16, 6, 70),
                new Programa("League of Legends", 2, 2.0, 2, 2, 15),
                new Programa("Minecraft", 4, 3.2, 4, 2, 4)
        };

        int opcion = 0;
        while (opcion != 6) {
            System.out.println("\n--- MENU ---");
            System.out.println("1) Computadora más económica");
            System.out.println("2) Computadora más cara");
            System.out.println("3) Elegir computadora");
            System.out.println("4) Computadora según necesidades del cliente");
            System.out.println("5) Mostrar programas que puede correr una computadora");
            System.out.println("6) Salir");
            System.out.print("Opción: ");
            opcion = sc.nextInt();

            if (opcion == 1) {
                mostrarMasEconomica(pcs);
            } else if (opcion == 2) {
                mostrarMasCara(pcs);
            } else if (opcion == 3) {
                elegirComputadora(pcs);
            } else if (opcion == 4) {
                recomendarPorProgramas(pcs, programas);
            } else if (opcion == 5) {
                mostrarProgramasPorComputadora(pcs, programas);
            } else if (opcion == 6) {
                System.out.println("Saliendo...");
            } else {
                System.out.println("Opción inválida");
            }
        }
    }

    static void mostrarMasEconomica(Computadora[] pcs) {
        Computadora min = pcs[0];
        for (int i = 1; i < pcs.length; i++) {
            if (pcs[i].precio < min.precio) {
                min = pcs[i];
            }
        }
        System.out.println("Más económica: " + min.mostrar());
    }

    static void mostrarMasCara(Computadora[] pcs) {
        Computadora max = pcs[0];
        for (int i = 1; i < pcs.length; i++) {
            if (pcs[i].precio > max.precio) {
                max = pcs[i];
            }
        }
        System.out.println("Más cara: " + max.mostrar());
    }

    static void elegirComputadora(Computadora[] pcs) {
        for (int i = 0; i < pcs.length; i++) {
            System.out.println((i + 1) + ") " + pcs[i].mostrar());
        }
        System.out.print("Seleccione número: ");
        int idx = sc.nextInt() - 1;
        if (idx >= 0 && idx < pcs.length) {
            System.out.println("Seleccionada: " + pcs[idx].mostrar());
        } else {
            System.out.println("Índice inválido");
        }
    }

    static void recomendarPorProgramas(Computadora[] pcs, Programa[] programas) {
        int hilosMax = 0, ramMax = 0, vramMax = 0, almacenamientoTotal = 0;
        double frecMax = 0;

        String continuar = "s";
        while (continuar.equalsIgnoreCase("s")) {
            for (int i = 0; i < programas.length; i++) {
                System.out.println((i + 1) + ") " + programas[i].mostrar());
            }
            System.out.print("Seleccione programa: ");
            int idx = sc.nextInt() - 1;
            if (idx >= 0 && idx < programas.length) {
                Programa p = programas[idx];
                if (p.hilos > hilosMax) hilosMax = p.hilos;
                if (p.frecuencia > frecMax) frecMax = p.frecuencia;
                if (p.ram > ramMax) ramMax = p.ram;
                if (p.vram > vramMax) vramMax = p.vram;
                almacenamientoTotal += p.almacenamiento;
            }
            System.out.print("¿Agregar otro programa? (s/n): ");
            continuar = sc.next();
        }

        System.out.println("Requisitos: Hilos=" + hilosMax + " Frec=" + frecMax + " RAM=" + ramMax +
                " VRAM=" + vramMax + " Almacenamiento=" + almacenamientoTotal);

        for (int i = 0; i < pcs.length; i++) {
            Computadora c = pcs[i];
            if (c.hilos >= hilosMax && c.frecuencia >= frecMax && c.ram >= ramMax &&
                    c.vram >= vramMax && c.almacenamiento >= almacenamientoTotal) {
                System.out.println("Compatible: " + c.mostrar());
            }
        }
    }

    static void mostrarProgramasPorComputadora(Computadora[] pcs, Programa[] programas) {
        for (int i = 0; i < pcs.length; i++) {
            System.out.println((i + 1) + ") " + pcs[i].mostrar());
        }
        System.out.print("Seleccione computadora: ");
        int idx = sc.nextInt() - 1;
        if (idx >= 0 && idx < pcs.length) {
            Computadora pc = pcs[idx];
            System.out.println("Programas que puede correr:");
            for (int j = 0; j < programas.length; j++) {
                Programa p = programas[j];
                if (pc.hilos >= p.hilos && pc.frecuencia >= p.frecuencia &&
                        pc.ram >= p.ram && pc.vram >= p.vram && pc.almacenamiento >= p.almacenamiento) {
                    System.out.println("- " + p.mostrar());
                }
            }
        } else {
            System.out.println("Índice inválido");
        }
    }
}


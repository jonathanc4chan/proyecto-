# proyecto-

import java.util.Scanner;

import java.util.ArrayList;

import java.util.List;

// Interfaz para los productos (sillas y mesas)

interface Furniture {

    void create();
}

// Clase concreta para sillas
class Chair implements Furniture {
    private String style;
    private String color;
    private String material;

    public Chair(String style, String color, String material) {
        this.style = style;
        this.color = color;
        this.material = material;
    }

    @Override
    public void create() {
        System.out.println("Se ha creado una silla " + style + " de color " + color + " hecha de " + material + ".");
    }
}

// Clase concreta para mesas
class Table implements Furniture {
    private String style;
    private String color;
    private String material;

    public Table(String style, String color, String material) {
        this.style = style;
        this.color = color;
        this.material = material;
    }

    @Override
    public void create() {
        System.out.println("Se ha creado una mesa " + style + " de color " + color + " hecha de " + material + ".");
    }
}

// Clase para representar una venta
class Sale {
    private String productName;
    private double price;
    private String deliveryDate;
    private String customerName;
    private String nit;
    private String saleNumber;

    public Sale(String productName, double price, String deliveryDate, String customerName, String nit, String saleNumber) {
        this.productName = productName;
        this.price = price;
        this.deliveryDate = deliveryDate;
        this.customerName = customerName;
        this.nit = nit;
        this.saleNumber = saleNumber;
    }

    public void displaySaleInfo() {
        System.out.println("\nDetalles de la venta:");
        System.out.println("Producto: " + productName);
        System.out.println("Precio: " + price);
        System.out.println("Fecha de Entrega: " + deliveryDate);
        System.out.println("Nombre del Cliente: " + customerName);
        System.out.println("NIT: " + nit);
        System.out.println("Número de Venta: " + saleNumber);
    }
}

// Fábrica abstracta para crear productos Furniture
abstract class FurnitureFactory {
    // El método factoryMethod que debe ser implementado por las subclases
    public abstract Furniture createFurniture(String style, String color, String material);
}

// Fábrica concreta para sillas
class ChairFactory extends FurnitureFactory {
    @Override
    public Furniture createFurniture(String style, String color, String material) {
        return new Chair(style, color, material);
    }
}

// Fábrica concreta para mesas
class TableFactory extends FurnitureFactory {
    @Override
    public Furniture createFurniture(String style, String color, String material) {
        return new Table(style, color, material);
    }
}

public class Fabrica {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        List<Sale> sales = new ArrayList<>();

        System.out.println("Crear una silla:");
        System.out.print("Estilo: ");
        String chairStyle = scanner.nextLine();
        System.out.print("Color: ");
        String chairColor = scanner.nextLine();
        System.out.print("Material: ");
        String chairMaterial = scanner.nextLine();
        System.out.print("Precio: ");
        double chairPrice = scanner.nextDouble();
        scanner.nextLine();  // Consume la nueva línea pendiente
        System.out.print("Fecha de Entrega: ");
        String chairDeliveryDate = scanner.nextLine();
        System.out.print("Nombre del Cliente: ");
        String customerName = scanner.nextLine();
        System.out.print("NIT: ");
        String nit = scanner.nextLine();
        System.out.print("Número de Venta: ");
        String saleNumber = scanner.nextLine();

        FurnitureFactory chairFactory = new ChairFactory();
        Furniture chair = chairFactory.createFurniture(chairStyle, chairColor, chairMaterial);
        chair.create();

        Sale chairSale = new Sale("Silla", chairPrice, chairDeliveryDate, customerName, nit, saleNumber);
        sales.add(chairSale);

        System.out.println("\nCrear una mesa:");
        System.out.print("Estilo: ");
        String tableStyle = scanner.nextLine();
        System.out.print("Color: ");
        String tableColor = scanner.nextLine();
        System.out.print("Material: ");
        String tableMaterial = scanner.nextLine();
        System.out.print("Precio: ");
        double tablePrice = scanner.nextDouble();
        scanner.nextLine();  // Consume la nueva línea pendiente
        System.out.print("Fecha de Entrega: ");
        String tableDeliveryDate = scanner.nextLine();
        System.out.print("Nombre del Cliente: ");
        customerName = scanner.nextLine();
        System.out.print("NIT: ");
        nit = scanner.nextLine();
        System.out.print("Número de Venta: ");
        saleNumber = scanner.nextLine();

        FurnitureFactory tableFactory = new TableFactory();
        Furniture table = tableFactory.createFurniture(tableStyle, tableColor, tableMaterial);
        table.create();

        Sale tableSale = new Sale("Mesa", tablePrice, tableDeliveryDate, customerName, nit, saleNumber);
        sales.add(tableSale);

        // Mostrar información de ventas
        for (Sale sale : sales) {
            sale.displaySaleInfo();
                }
    }
}

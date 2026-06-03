classDiagram
class Producto {
    -String nombre
    -double precioBase
    +Producto(String nombre, double precioBase)
    +getPrecioBase() double
}

class CalculadoraIVA {
    -double IVA
    +calcularPrecioFinal(double precio) double
}

class Main {
    +main(args: String[]) void
}

class Scanner {
    <<External>>
}

Main ..> Producto : "crea instancia"
Main ..> CalculadoraIVA : "usa para calcular"
Main ..> Scanner : "lee entrada"

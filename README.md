```mermaid
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



```mermaid
sequenceDiagram
autonumber
actor Usuario
participant M as Main
participant S as Scanner
participant P as Producto
participant C as CalculadoraIVA

Usuario->>M: Ejecuta el programa
M->>S: new Scanner(System.in)
M->>Usuario: "Nombre del producto: "
Usuario-->>M: "Camiseta"
M->>Usuario: "Precio base: "
Usuario-->>M: 20.0
M->>P: new Producto("Camiseta", 20.0)
activate P
P-->>M: instancia creada
deactivate P
M->>C: calcularPrecioFinal(20.0)
activate C
Note over C: Aplica IVA (21%)
C-->>M: 24.2
deactivate C
M->>Usuario: Imprime "Total con IVA: 24.2"

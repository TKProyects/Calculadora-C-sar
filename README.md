Diagramas del Proyecto

Aquí tienes los diagramas de clases y de secuencia del proyecto perfectamente renderizados.

1. Diagrama de Clases

Este diagrama muestra la estructura estática de tus clases.

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

Main ..> Producto : "instancia"
Main ..> CalculadoraIVA : "usa"
Main ..> Scanner : "usa"


2. Diagrama de Secuencia

Este diagrama muestra el flujo de ejecución paso a paso en el tiempo.

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
M->>P: new Producto ("Camiseta", 20.0)
activate P
P-->>M: instancia creada
deactivate P
M->>C: calcularPrecioFinal(20.0)
activate C
Note over C: Aplica IVA (21%)
C-->>M: 24.2
deactivate C
M->>Usuario: Imprime "Total con IVA: 24.2"


README - Calculadora Pixel ArtDescripciónEsta es una Calculadora Pixel Art diseñada con un estilo retro, que permite realizar operaciones matemáticas básicas. Su diseño está inspirado en el arte pixelado, con un enfoque en la estética de los gráficos de los años 80.CaracterísticasInterfaz amigable: La calculadora es fácil de usar, con botones grandes y claros.Operaciones básicas: Soporta suma, resta, multiplicación y división.Teclado accesible: También puedes usar el teclado para realizar cálculos.Efectos visuales: Incluye efectos de sombras y gradientes, mejorando la experiencia de usuario.Estructura del Código1. HTMLEl archivo HTML define la estructura básica de la calculadora, organizando todos los elementos necesarios para su funcionamiento:Encabezado: Contiene metadatos y enlaces a estilos CSS.Cuerpo: Define la interfaz de usuario, incluyendo la pantalla de la calculadora y los botones.2. CSSEl estilo está definido en una etiqueta <style> dentro del <head>. Aquí se establecen:Variables CSS: Para colores y tamaños que permiten una fácil personalización.Estilos de botones: Efectos visuales al interactuar con ellos.Diseños responsivos: Permite que la calculadora se ajuste a diferentes tamaños de pantalla.3. JavaScriptEl script al final del archivo maneja la lógica de la calculadora:Variables: Almacena el número actual y la operación seleccionada.Funciones:
formatForDisplay: Formatea el número para mostrarlo correctamente en la pantalla.
updateScreen: Actualiza la pantalla de la calculadora con los números y operaciones.
Métodos para manejar la entrada de números, operaciones y acciones del usuario.

4. InteractividadLa calculadora responde a eventos de clic y teclado, permitiendo a los usuarios realizar operaciones de forma intuitiva. Las funciones se activan según la interacción del usuario, ya sea a través de botones o teclas.UsoAbre el archivo HTML en tu navegador.Utiliza el ratón o el teclado para realizar cálculos.Presiona Esc para borrar todo o Backspace para borrar el último dígito.Contribuciones¡Las mejoras son bienvenidas! Si deseas contribuir, por favor haz un fork del repositorio y envía un pull request.LicenciaEste proyecto es de código abierto y se puede utilizar bajo la licencia MIT.


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

Main ..> Producto : "instancia"
Main ..> CalculadoraIVA : "usa"
Main ..> Scanner : "usa"
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
M->>C: calcular PrecioFinal (20.0)
activate C
Note over C: Aplica IVA (21%)
C-->>M: 24.2
deactivate C
M->>Usuario: Imprime "Total con IVA: 24.2"

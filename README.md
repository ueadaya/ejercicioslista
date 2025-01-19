# ejercicioslista

namespace EjerciciosListasPOO
{
    // Ejercicio 1
    class Ejercicio1
    {
        public void MostrarAsignaturas()
        {
            List<string> asignaturas = new List<string> { "Matemáticas", "Física", "Química", "Historia", "Lengua" };
            Console.WriteLine("Asignaturas del curso:");
            foreach (var asignatura in asignaturas)
            {
                Console.WriteLine(asignatura);
            }
        }
    }

    // Ejercicio 2
    class Ejercicio2
    {
        public void MostrarEstudioAsignaturas()
        {
            List<string> asignaturas = new List<string> { "Matemáticas", "Física", "Química", "Historia", "Lengua" };
            foreach (var asignatura in asignaturas)
            {
                Console.WriteLine($"Yo estudio {asignatura}");
            }
        }
    }

    // Ejercicio 3
    class Ejercicio3
    {
        public void MostrarNotas()
        {
            List<string> asignaturas = new List<string> { "Matemáticas", "Física", "Química", "Historia", "Lengua" };
            Dictionary<string, double> notas = new Dictionary<string, double>();

            foreach (var asignatura in asignaturas)
            {
                Console.Write($"Introduce la nota para {asignatura}: ");
                double nota = Convert.ToDouble(Console.ReadLine());
                notas[asignatura] = nota;
            }

            Console.WriteLine("\nNotas obtenidas:");
            foreach (var item in notas)
            {
                Console.WriteLine($"En {item.Key} has sacado {item.Value}");
            }
        }
    }

    // Ejercicio 4
    class Ejercicio4
    {
        public void MostrarLoteriaOrdenada()
        {
            Console.WriteLine("Introduce los números ganadores de la lotería (separados por espacio):");
            string[] numeros = Console.ReadLine().Split(' ');
            List<int> numerosLoteria = numeros.Select(int.Parse).ToList();
            numerosLoteria.Sort();

            Console.WriteLine("Números ganadores ordenados de menor a mayor:");
            Console.WriteLine(string.Join(", ", numerosLoteria));
        }
    }

    // Ejercicio 5
    class Ejercicio5
    {
        public void MostrarListaInversa()
        {
            List<int> numeros = Enumerable.Range(1, 10).ToList();
            numeros.Reverse();
            Console.WriteLine("Números del 1 al 10 en orden inverso:");
            Console.WriteLine(string.Join(", ", numeros));
        }
    }

    // Clase principal
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Selecciona el ejercicio a ejecutar (1-5):");
            int opcion = Convert.ToInt32(Console.ReadLine());

            switch (opcion)
            {
                case 1:
                    new Ejercicio1().MostrarAsignaturas();
                    break;
                case 2:
                    new Ejercicio2().MostrarEstudioAsignaturas();
                    break;
                case 3:
                    new Ejercicio3().MostrarNotas();
                    break;
                case 4:
                    new Ejercicio4().MostrarLoteriaOrdenada();
                    break;
                case 5:
                    new Ejercicio5().MostrarListaInversa();
                    break;
                default:
                    Console.WriteLine("Opción no válida.");
                    break;
            }

            Console.WriteLine("\nPresiona cualquier tecla para salir...");
            Console.ReadKey();
        }
    }
}

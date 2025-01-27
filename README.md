# Tarea-Semana-07
# Resolución de problemas con pilas en C#

Este repositorio contiene soluciones en C# para los siguientes problemas:

* **Verificación de balanceo de expresiones matemáticas:** Utiliza una pila para verificar si los paréntesis en una expresión matemática están correctamente balanceados.
* **Torres de Hanoi:** Implementación recursiva del clásico problema de las Torres de Hanoi.
using System;
using System.Collections.Generic;

public class BalanceoExpresiones
{
    public static bool EsBalanceada(string expresion)
    {
        Stack<char> pila = new Stack<char>();

        foreach (char c in expresion)
        {
            if (c == '(' || c == '{' || c == '[')
                pila.Push(c);
            else if (c == ')' || c == '}' || c == ']')
            {
                if (pila.Count == 0)
                    return false; // No hay paréntesis abierto para cerrar
                char abierto = pila.Pop();
                if ((c == ')' && abierto != '(') ||
                    (c == '}' && abierto != '{') ||
                    (c == ']' && abierto != '['))
                    return false; // Paréntesis no coinciden
            }
        }

        return pila.Count == 0; // Si la pila está vacía, todos los paréntesis están balanceados
    }
}
public class TorresHanoi
{
    public static void ResolverHanoi(int n, char origen, char auxiliar, char destino)
    {
        if (n == 1)
        {
            Console.WriteLine("Mover disco 1 de {0} a {1}", origen, destino);
        }
        else
        {
            ResolverHanoi(n - 1, origen, destino, auxiliar);
            Console.WriteLine("Mover disco {0} de {0} a {1}", n, origen, destino);
            ResolverHanoi(n - 1, auxiliar, origen, destino);
        }
    }
}

**Instrucciones de uso:**
...

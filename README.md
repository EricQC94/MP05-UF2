# Activitats: 

Per dibuixar els diagrames de flux podeu fer servir [draw.io](https://draw.io) o qualsevol altra eina online.

1. Calcula el CC de les següents figures:
  - ![image](https://user-images.githubusercontent.com/110727546/204613022-4ab64342-2e06-438d-a7e8-570685b3c406.png)
  - ![image](https://user-images.githubusercontent.com/110727546/204613180-6d55bf09-28b8-417e-96f4-f71a762ac44c.png)
  - ![image](https://user-images.githubusercontent.com/110727546/204655229-8c3f28d7-3d8b-4746-a55d-331f89da39d2.png)

  - **Resultat 1: 15 - 14 + 2 = 3**
  - **Resultat 2: 16 - 14 + 2 = 4**
  - **Resultat 3: 8 - 6 + 2 = 4**


2. Dibuixa el diagrama de flux representat per aquest codi i després calcula la seva CC:
  - ![image](https://user-images.githubusercontent.com/110727546/204615125-363e5e6c-173b-4ec0-8c0b-cb97985ade06.png)

  - **Diagrama: ![Exercici 2](https://user-images.githubusercontent.com/113598440/204747451-77272cbf-3bf9-4cdb-8ed0-64c7d5f33f9c.jpg)**

  - **Resultat CC: 7 - 6 + 2 = 3**

3. Dibuixa el diagrama de flux representat per aquest codi i després calcula la seva CC:

```
public class proves {
    public static  String queEmPoso(int temperatura) {
        String roba = "res";
        if(temperatura<0){
           roba = "roba d'esquiar";
        }
        else if(temperatura<10){
           roba = "roba de muntanya";
        }
        else if(temperatura<20){
           roba = "roba d'hivern";
        }
        else if(temperatura<30){
           roba = "roba d'estiu";
        }
        return roba;
    }    
}
```

  - **Diagrama: ![Diagrama sense títol](https://user-images.githubusercontent.com/113598440/204753444-95fbb414-e15e-4abe-8fd7-420955ebfa8e.jpg)**
  - **Resultat CC: 12 - 10 + 2 = 4**

4. Dibuixa el diagrama de flux representat per aquest codi, calcula la seva CC i crea una prova per a cada camí posible:

```
    public static Boolean llumsEncesos(int hora) {
        Boolean llums = false;
        if(hora <= 8 || hora >= 20){
            llums = true;
        }
        return llums;
    }
```
  - **Diagrama:![diagrama llums](https://user-images.githubusercontent.com/113598440/204757724-6fe0aeb2-31e9-4b60-867e-e29934bab5eb.jpg)**
 
  - **Resultat CC: 3 - 4 + 2 = 1** 
  - **Resultat proves camins:** 

5. Investiga sobre les proves de caixa negra:

  - Què són?
  És un mètode de testing de software basat en els inputs i outputs.
  - Quina diferència principal tenen sobre les de caixa blanca?
Els mètodes de caixa blanca validen l'estructura interna del codi software, mentre que els de caixa negra validen els requeriments funcionals, a part de facilitar les proves de comunicació entre mòduls.

## Activitats Caixa Negra:

Pizzeria Pepe:

Codi font:
```
public class pizzeriaPepe {
    public static void main(String[] args) {
        System.out.println(potCarregar(5));
    }
    public static boolean potCarregar(int pizzes){
        boolean pot = false;
        if(pizzes <=10 && pizzes >= 1){
            pot = true;
        }
        return pot;
    }

}
```
Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Pizzes | És un número sencer? + rang valors (1..10) | 1- pizzes <= 1 pizzes <= 10| 2- pizzes > 10 <br> 3- pizzes < 1 <br> 4- no és un número |

Classes d'equivalència vàlides:
| true | 
| ----------- |
| 1- 1 <= pizzes <= 10 |

Classes d'equivalència no vàlides:
| false |
| ----------- |
| 2- pizzes > 10 | 
| 3- pizzes < 1 |

Error:
| Error |
| ----------- |
| 4- No és un número | 

Proves:
| Pizzes |
| ----------- |
| 1- 5 = true |
| 2- 30 = false |
| 3- -3 = false |
| 4- nou = error |


Valors límit:
| Pizzes |
| ----------- |
| 5- 0 = false |
| 6- 1 = true |
| 7- 2 = true |
| 8- 9 = true |
| 9- 10 = true |
| 10- 11 = false |


Transports Jean Claude:

```
public class jeanClaude
{
    public static void main(String[] args) {
        System.out.println(potCarregar(600, 900)); //Introduir dades
    }
    public static int potCarregar(int carrega, int capacitat)
    {
        int resultat;
        if (carrega >= 500 && carrega <= 900 && capacitat>= 500 && capacitat <= 750 && carrega<=capacitat) resultat = 0;
        else resultat = -1;

        return resultat;
    }
}
```

Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Càrrega | 1- És un número? | 2- carrega => 500 | 3- carrega <= 900| 4- capacitat >= 500 | 5- capacitat <= 750 | 6- carrega <= capacitat |

Classes d'equivalència vàlides:
| true |
| ----------- |
| 1- 500 <= carrega <=750 |

Classes d'equivalència no vàlides:
| false |
| ----------- |
| 2- carrega > 750 |
| 3- carrega < 500 |

Error:
| Error |
| ----------- |
| 4. no és un número |

Proves:
| carrega |
| ----------- |
| 1- 610 = true |
| 2- 900 = false |
| 3- 0 = false |
| 4- vint = error |


Valor límit:
| carrega |
| ----------- |
| 5- 499 = false |
| 6- 500 = true |
| 7-  501 = true |
| 8- 699 = true |
| 9- 700 = true |
| 10- 701 = false |


Control de temperatura:


```
public class ControlTemp {

    public static int calcularTemp(int medidor, int termostat) {
        int sortida = 0;
        int aux = termostat - medidor;
        if (medidor > termostat) {
            sortida = 0;
        } else if (aux == 0 || aux == 1 || aux == -1 || aux == 2 || aux == -2) {
            sortida = 1;
        } else {
            sortida = 2;
        }


        return sortida;
    }
}
```



Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| temperatura | És un número sencer? | 1- temperatura =< 50 | 2- temperatura >= -10 | 
| termostat | És un número sencer? | 1- termostat >= 15 | 2- termostat <= 40 |


Classes d'equivalència vàlides:
| true |
| ----------- | 
| 1- -10=< temperatura <= 50 |
| 2- 15 <= termostat <= 40 |


Classes d'equivalència no vàlides:
| false |
  | ----------- | 
| 3- temperatura > 50 |
| 4- termostat < 15 |

Error:
| Error |
  | ----------- | 
| 5- no és un número |

Proves:
  | ----------- | 
| temperatura i termostat |
| 1- 10 / 30 = true |
| 2- -15 / 50 = false |
| 3- -10 / 40 = false |
| 4- deu = error |


Valor límit:
| temperatura i termostat |
  | ----------- | 
| 5- -11 / 14 = false |
| 6- -10 / 15 = true |
| 7- -9 / 16 = true |
| 8- 49 / 39 = true |
| 9- 50 / 40 = true |
| 10- 51 / 41 = false |

## Activitats debug:

### Factorial:

El factorial d'un nombre és el resultat de multiplicar el número per ell mateix -1 tantes vegades com  siguin necessàries fins arrivar a 1.

Per exemple el factorial de 5 és:

5 * 4 * 3 * 2 * 1

![image](https://user-images.githubusercontent.com/110727546/206031980-55e59610-42bb-4cc6-9b5f-039d7f67e185.png)

Fes una funció factorial que rebi un número com paràmetre i retorni el seu factorial.

Es demana:

- Codi del programa.
- Captura de pantalla amb un punt d'interrupció que deixi veure totes les crides a la funció (agafeu un valor menor a 10).

```
import java.util.Scanner;

public class factorDecomp {
    public static void main(String args[]) {
        int numero;
        Scanner sc = new Scanner(System.in);
        System.out.println("Introdueix un numero: ");
        numero = sc.nextInt();

        for (int i = 2; i < numero; i++) {
            while (numero % i == 0) {
                System.out.println(i + " ");
                numero = numero / i;
            }
        }
        if (numero > 2) {
            System.out.println(numero);
        }
    }
}
```
Captura:

![Selecció_200](https://user-images.githubusercontent.com/113598440/209587750-dd7d45f7-3240-4841-ba21-4e6e5f2c606f.png)

### Taula de multiplicar:

Fes un programa que crea una matriu de números del 1 al 10.
Aquest programa rep per argument d'entrada un número sencer i retorna per terminal la taula de multiplicar d'aquest número multiplicant el argument per cada valor de la matriu.

Es demana:

- Codi del programa.
```
import java.util.Scanner;

public class taulaMult {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introdueix un enter: ");
        int num = scanner.nextInt();

        int[] multiples = new int[10];
        for (int i = 0; i < multiples.length; i++) {
            multiples[i] = (i + 1) * num;
        }

        System.out.println("La taula de multiplicació del " + num + " és:");
        for (int i = 0; i < multiples.length; i++) {
            System.out.println((i + 1) + " * " + num + " = " + multiples[i]);
        }
    }
}
```

- Captura de pantalla de com li passeu a IntelliJ com argument del programa un número. (Mireu exemple findAverage).
![Selecció_201](https://user-images.githubusercontent.com/113598440/209889413-6f62504f-7905-41f1-8b11-5b382dd1407d.png)

- Captura de com feu un punt d'interrupció al bucle de creació de la matriu i mostreu els valors de la matriu.
- Captura de punt d'interrupció al bucle de multiplicació i com modifiqueu a ma els valors de la matriu de números per a que l'execució retorni el número 1 10 vegades quan l'argument d'entrada era 1.


## Activitats proves unitaries
# Pizzeria Pepe

Codi del programa:

```
public class pizzeriaPepe {
    public static boolean potCarregar(int pizzes){
        boolean pot = false;
        if(pizzes <=10 && pizzes >= 1){
            pot = true;
        }
        return pot;
    }


```

Codi programa test:

```
import org.junit.jupiter.api.*;


class pizzeriaPepeTest {


    @Test
        //Valor entre els límits
    void prova1() {
        boolean pot = pizzeriaPepe.potCarregar(3);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor superior al límit superior
    void prova2() {
        boolean pot = pizzeriaPepe.potCarregar(11);
        Assertions.assertFalse(pot);
    }


    @Test
        //Valor inferior al límit inferior
    void prova3() {
        boolean pot = pizzeriaPepe.potCarregar(-2);
        Assertions.assertFalse(pot);
    }


    @Test
        //Valor no és un número
    void prova4() {
        boolean pot = pizzeriaPepe.potCarregar(Integer.parseInt("cinc"));
        Assertions.assertFalse(pot);
    }

    @Test
        //Valors limits
    void prova5() {
        boolean pot = pizzeriaPepe.potCarregar(0);
        Assertions.assertFalse(pot);
    }

    @Test
        //Valors limit
    void prova6() {
        boolean pot = pizzeriaPepe.potCarregar(1);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor entre els límits
    void prova7() {
        boolean pot = pizzeriaPepe.potCarregar(2);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor entre els límits
    void prova8() {
        boolean pot = pizzeriaPepe.potCarregar(9);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor entre els límits
    void prova9() {
        boolean pot = pizzeriaPepe.potCarregar(10);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor entre els límits
    void prova10() {
        boolean pot = pizzeriaPepe.potCarregar(11);
        Assertions.assertFalse(pot);
    }


}
```

# Jean Claude

Codi del programa:
```
public class jeanClaude {
    public static void main(String[] args) {
        System.out.println(carrega(600));
        System.out.println(capacitat(100));
    }
    public static boolean carrega(int carregaTotal) {
        boolean carrega = false;
        if(carregaTotal >= 500 && carregaTotal <=900){
            carrega = true;
        }
        return carrega;

    }
    public static boolean capacitat(int capacitatTotal){
        boolean capacitat = false;
        if(capacitatTotal >= 500 && capacitatTotal <= 700){
            capacitat = true;
        }
        return capacitat;
    }

}
```

Codi programa test:
```
import org.junit.jupiter.api.Test;

import static org.junit.Assert.assertEquals;

class TransportsJeanClaudeTest
{

    @Test
    void prova1() {
        assertEquals(-1, TransportsJeanClaude.potCarregar(400, 750)); // Correcte ja que no es pot portar

    }
    @Test
    void prova2() {

        assertEquals(-1, TransportsJeanClaude.potCarregar(500, 750)); //Error, la càrrega si que es pot portar, hauría de ser 0

    }
    @Test
    void prova3() {

        assertEquals(0, TransportsJeanClaude.potCarregar(400, 750)); //Error, la carrega no es pot portar sería -1
    }

    @Test
    void prova4() {

        assertEquals(0, TransportsJeanClaude.potCarregar(600, 750)); // Correcte, la càrrega es troba dins dels límits llavors si que es pot portar
    }
```

# Control temperatura:

Codi del programa:
```
public class ControlTemp {

    public static int calcularTemp(int medidor, int termostat) {
        int sortida = 0;
        int aux = termostat - medidor;
        if (medidor > termostat) {
            sortida = 0;
        } else if (aux == 0 || aux == 1 || aux == -1 || aux == 2 || aux == -2) {
            sortida = 1;
        } else {
            sortida = 2;
        }


        return sortida;
    }
}

```

Codi programa test:
```
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

class ControlTemperaturaTest
{

    @Test
    void prova1() {
        // Potencia és 2 temperatura > termostat, correcte
        assertEquals(2, ControlTemperatura.calcularPotencia(20, 15));
    }

    @Test
    void prova2() {
        // Potencia és 0 ja que tenim temperatura > termostat, dona error
        assertEquals(1, ControlTemperatura.calcularPotencia(20, 15));
    }

    @Test
    void prova3() {
        // Correcte, potencia major o menor en 0 a 2 graus respecte al termostat
        assertEquals(1,ControlTemperatura.calcularPotencia(23, 25));
        assertEquals(1,ControlTemperatura.calcularPotencia(27, 25));
    }

    @Test
    void prova4() {
        // Error, potencia m
        assertEquals(1,ControlTemperatura.calcularPotencia(22, 25));
        assertEquals(1,ControlTemperatura.calcularPotencia(28, 25));
    }

    @Test
    void prova5() {
        // Correcte
        assertEquals(2,ControlTemperatura.calcularPotencia(22, 25));
    }
    @Test
    void prova6() {
        // Error
        assertEquals(2,ControlTemperatura.calcularPotencia(26, 25));

    }


}
```

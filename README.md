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

### Pizzeria Pepe:

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
<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Pizzes | És un número sencer? + rang valors (1..10) | 1- pizzes <= 1 pizzes <= 10| 2- pizzes > 10 <br> 3- pizzes < 1 <br> 4- no és un número |

<br>Classes d'equivalència vàlides:
| true | 
| ----------- |
| 1- 1 <= pizzes <= 10 |

<br>Classes d'equivalència no vàlides:
| false |
| ----------- |
| 2- pizzes > 10 | 
| 3- pizzes < 1 |

<br>Error:
| Error |
| ----------- |
| 4- No és un número | 

<br>Proves:
| Pizzes |
| ----------- |
| 1- 5 = true |
| 2- 30 = false |
| 3- -3 = false |
| 4- nou = error |


<br>Valors límit:
| Pizzes |
| ----------- |
| 5- 0 = false |
| 6- 1 = true |
| 7- 2 = true |
| 8- 9 = true |
| 9- 10 = true |
| 10- 11 = false |


### Transports Jean Claude:

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
<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Càrrega | 1- És un número? | 2- carrega => 500 | 3- carrega <= 900| 4- capacitat >= 500 | 5- capacitat <= 750 | 6- carrega <= capacitat |

<br>Classes d'equivalència vàlides:
| true |
| ----------- |
| 1- 500 <= carrega <=750 |

<br>Classes d'equivalència no vàlides:
| false |
| ----------- |
| 2- carrega > 750 |
| 3- carrega < 500 |

<b>Error:
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


<br>Valor límit:
| carrega |
| ----------- |
| 5- 499 = false |
| 6- 500 = true |
| 7-  501 = true |
| 8- 699 = true |
| 9- 700 = true |
| 10- 701 = false |


### Control de temperatura:

Un programa gestiona el modificador de temperatura del sistema de calefacció d'un restaurant.

Aquest programa rep la medició de la temperatura del restaurant en graus celsius, acceptant com entrades vàlides de -10 a 50 graus. (medidor)

A més té una entrada d'usuari/a amb la temperatura que es vol mantenir, que va de 15 a 40 graus. (termostat).

El sistema té tres sortides possibles que representen la potencia del sistema de calefacció: 0, 1, 2.

Segons la informació que té en cada moment el programa farà el següent:

Si la temperatura del medidor és més alta que la del termostat, la potencia del sistema serà 0.
Si la temperatura del medidor és més baixa o més alta que la del termostat però només entre 0 i 2 graus, la potència serà 1.
Si la temperatura del medidor és més baixa que la del termostat en més de dos graus, la potència del sistema serà 2.

Es demana:

- Fer el codi font del programa.
- Fer la taula amb les particions equivalents i casos vàlids i no vàlids.
- Fer la taula amb l'anàlisis de valors límit i casos vàlids i no vàlids.

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


```
<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Càrrega | 1- És un número? | 2- carrega => 500 | 3- carrega <= 900| 4- capacitat >= 500 | 5- capacitat <= 750 | 6- carrega <= capacitat |

<br>Classes d'equivalència vàlides:
| true |
| 1- 500 <= carrega <=750 |

<br>Classes d'equivalència no vàlides:
| false |
| 2- carrega > 750 |
| 3- carrega < 500 |

<b>Error:
| Error |
| 4. no és un número |

Proves:
| carrega |
| 1- 610 = true |
| 2- 900 = false |
| 3- 0 = false |
| 4- vint = error |


Valor límit:
| carrega |
| 5- 499 = false |
| 6- 500 = true |
| 7-  501 = true |
| 8- 699 = true |
| 9- 700 = true |
| 10- 701 = false |

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


class provesPizzeria {


    @Test
        //Valor entre els límits
    void prova1() {
        boolean pot = pizzeriaPepe.potCarregar(4);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor superior al límit superior
    void prova2() {
        boolean pot = pizzeriaPepe.potCarregar(13);
        Assertions.assertFalse(pot);
    }


    @Test
        //Valor inferior al límit inferior
    void prova3() {
        boolean pot = pizzeriaPepe.potCarregar(0);
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
        boolean pot = pizzeriaPepe.potCarregar(1);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valors limit
    void prova6() {
        boolean pot = pizzeriaPepe.potCarregar(10);
        Assertions.assertTrue(pot);
    }

    @Test
        //Valor entre els límits
    void prova7() {
        boolean pot = pizzeriaPepe.potCarregar(0);
        Assertions.assertFalse(pot);
    }

    @Test
        //Valor superior al límit superior
    void prova8() {
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
import org.junit.jupiter.api.Assertions;
import org.junit.jupiter.api.Test;

class provesJean
{
    //Classes d'equivalència vàlides
    @Test
    void prova1() {
        Assertions.assertEquals(0, jeanClaude.potCarregar(550, 550)); //Correcte

    }
    //Classes d'equivalència no vàlides
    @Test
    void prova2() {

        Assertions.assertEquals(0, jeanClaude.potCarregar(400, 900)); //No es pot portar la carrega, expected hauria de ser -1

    }

    //Valors límit - classes vàlides
    @Test
    void prova3() {

        Assertions.assertEquals(0, jeanClaude.potCarregar(500, 750));
    }

    @Test
    void prova4() {

        Assertions.assertEquals(0, jeanClaude.potCarregar(900, 750));
    }


    //Valors límit - classes no vàlides

    @Test
    void prova5() {

        Assertions.assertEquals(-1, jeanClaude.potCarregar(499, 901)); //Els dos valors no es poden carregar, retorna -1: correcte.
    }

    @Test
    void prova6() {
        Assertions.assertEquals(0, jeanClaude.potCarregar(901, 751)); //Valors que no es poden portar. Espera un -1 però fem fallar el programa.
    }


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

class provesTemp
{

    @org.junit.jupiter.api.Test
    void prova1() {
        // Classes d'equivalència vàlides - temperatura del medidor més baixa que la del termostat en diferencia de 2 graus (s'espera 1)
        assertEquals(1, ControlTemp.calcularTemp(-10, -8));
    }


    @org.junit.jupiter.api.Test
    void prova2() {
        // Valor límit vàlids
        assertEquals(2,ControlTemp.calcularTemp(-10, 50));
        assertEquals(2,ControlTemp.calcularTemp(-9, 49));
    }

    @org.junit.jupiter.api.Test
    void prova3() {
        // Valor límit no vàlids
        assertEquals(2,ControlTemp.calcularTemp(-11, 51));
        assertEquals(1,ControlTemp.calcularTemp(0, 0));
    }


    // ALTRES PROVES
    @org.junit.jupiter.api.Test
    void prova4() {
        // Medidor > termostat
        assertEquals(0,ControlTemp.calcularTemp(30, 25));
    }
    @Test
    void prova5() {
        // Fem fallar el programa
        assertEquals(2,ControlTemp.calcularTemp(26, 25));

    }


}
```

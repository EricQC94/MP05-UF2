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
import java.util.Scanner;

public class pizzeriaPepe {
    public static void main(String[] args) {
        Scanner ent = new Scanner(System.in);
        int pizzes;


        System.out.println("Introdueix un número de pizzes:");
        pizzes = ent.nextInt();

         if (1 < pizzes && pizzes < 10) {
            System.out.println("TRUE");
        }
        else{
            System.out.println("FALSE");
        }

    }
}
```
<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Pizzes | És un número? + rang valors (1..10) | 1. 1 <= pizzes <= 10| 2. pizzes == 0 <br>3. no és un número |

<br>Classes d'equivalència vàlides:
| Pizzes | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 4 | 1 | TRUE |

<br>Classes d'equivalència no vàlides:
| Pizzes | Classe no vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 0 | 2 | FALSE |
| cinc | 3 | no és un número |

Proves d'anàlisi dels valors límit:

| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Pizzes | És un número? + rang valors (1..10) | 4. pizzes=1 <br> 5. pizzes=10| 6. pizzes=0 <br> 7. pizzes=11|

Classes vàlides:
| Pizzes | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 1 | 5 | TRUE |
| 10 | 6 | TRUE |

Classes no vàlides:
| Pizzes | Classe no vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 0 | 5 | FALSE |
| 11 | 6 | FALSE |

### Transports Jean Claude:

```
import java.util.Scanner;

public class jeanClaude {
    public static void main(String[] args) {
        Scanner ent = new Scanner(System.in);
        int carrega;

        System.out.println("Introdueix un pes de càrrega:");
        carrega = ent.nextInt();

        if (carrega >= 500 && carrega < 750) {
            System.out.println("0");

        }
        else
        System.out.println("-1");
    }
}

```
<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Càrrega | És un número? + rang valors (500..750) | 1. 500 >= carrega <= 750| 2. carrega < 500 carrega > 750  <br>3. no és un número |


<br>Classes d'equivalència vàlides:
| Càrrega | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 550 | 1 | 0 |

<br>Classes d'equivalència no vàlides:
| Càrrega | Classe no vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 400 | 2 | -1 |
| 850 | 2 | -1 |
| cinquanta | 3 | no és un número |

Proves d'anàlisi dels valors límit:

| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Càrrega | És un número? + rang valors (500..750) | 4. carrega=500 <br> 5. carrega=750 <br> 6. carrega=501 <br>7. carrega=749 | 6. carrega=499 <br> 7. carrega=751|

Classes vàlides:
| Carrega | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 500 | 4 | 0 |
| 750 | 5 | 0 |
| 501 | 6 | 0 |
| 749 | 7 | 0 |

Classes no vàlides:
| Carrega | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| 499 | 6 | -1 |
| 751 | 7 | -1 |


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
    public static void main(String[] args) {
        System.out.println(controlTemp(1,2));
    }
    public static int controlTemp (int medidor, int termostat){
        int sortida = 0;
        int aux = termostat-medidor;
        if (medidor > termostat) {
            sortida = 0;
        }
        else if(aux==0 || aux ==1 || aux == -1 || aux ==2 || aux ==-2){
            sortida = 1;
        }else{
            sortida = 2;
        }


        return sortida;
    }
```



<br>Classes d'equivalència:
| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Temperatura | És un número? + rang valors (-10..50) | 1. -10 , x <= controlTemp <= y , 50| <br>2. no és un número |

<br>Classes d'equivalència vàlides:
| Temperatura | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| -10, 2 | 1 | 2 |

<br>Classes d'equivalència no vàlides:
| Temperatura | Classe no vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| cinc | 2 | no és un número |

Proves d'anàlisi dels valors límit:

| Paràmetre entrada | Regla a aplicar | Classes vàlides | Classes no vàlides |
| ----------- | ----------- | ----------- | ----------- |
| Temperatura | És un número? + rang valors (-10, x..y , 50) | 4. controlTemp=-10, 50 <br> 5. controlTemp= -9, 49| 6. controlTemp=-11, 51 <br> 7. controlTemp=-0, 0|

Classes vàlides:
| Temperatura | Classe vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| -10, 50 | 4 | 2 |
| -9, 49  | 5 | 2 |

Classes no vàlides:
| Temperatura | Classe no vàlida coberta| Resultat |
| ----------- | ----------- | ----------- |
| -11, 51 | 6 | 2 |
| -0, 0 | 7 | 1 | 


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
- Captura de pantalla de com li passeu a IntelliJ com argument del programa un número. (Mireu exemple findAverage).
- Captura de com feu un punt d'interrupció al bucle de creació de la matriu i mostreu els valors de la matriu.
- Captura de punt d'interrupció al bucle de multiplicació i com modifiqueu a ma els valors de la matriu de números per a que l'execució retorni el número 1 10 vegades quan l'argument d'entrada era 1.

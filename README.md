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

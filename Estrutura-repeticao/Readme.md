# Estrutura de repetição

Laços de repetição, também conhecidos como laços de iteração ou simplesmente loops, são comandos que permitem a iteração de codígo, ou seja, que comandos presentes no bloco sejam repetidos diversas vezes.

##

Laços ou repetições são representados pelas seguintes estruturas: 
 - <strong>*For*</strong> (para)
 - <strong>*While*</strong> (enquanto)
 - <strong>*Do While*</strong> (faça enquanto)

 ##

 ### <strong>*For*</strong>

 O comando `for` (na tradução literal para a língua portuguesa é "para") permite que uma variável contadora seja testade e incrementada a cada iteração, sendo essas informações definidas na chamada do comando. O comando `for` recebe como entrada uma variável contadora, a condição e o valor de incrementação.

 A estrutura de sintaxe do controle de repetição `for` é exibida abaixo:

 ```java
 // Estrutura de controle de fluxo for

 for (bloco de inicialização; expressão boleana de validação; bloco de atualização) {
    // Comando que será executado até que a expressão de validação torne-se falsa
 }
 ```
 
 Vamos imaginar que Joãozinho precisa contar até 20 carneirinhos para pegar no sono:

 ```java
public class ExemploFor {
    public static void main(String[] args) {
        for(int carneiro = 0; carneiro <= 20; carneiro++) {
            System.out.println("Contando carneiro: " + carneiro);
        }

        System.out.println("Joãozinho Dormiu!");
    } 
}
 ```

 Também usamos o `for` para interagir sobre arrays e coleções:

 ```java
 public class ExemploForArray {
    public static void main(String[] args) {
        String alunos[] = { "Pablo", "Biano", "Rebeca" };

        for(int x = 0; x < alunos.length; x++) {
            System.out.println("O aluno no índice x = " + x + " é " + alunos[x]);
        }
    }
}
 ```

 ##

 ### Break e Continue

 <strong>Break</strong> significa parar, quebrar, frear, interromper. E é isso que se faz quando o Java encontra esse comando pela frente. <strong>Continue</strong>, como o nome diz, ele "continua" o laço. O comando `break` interrompe o laço, já o `continue` interrompe somente a iteração atual.

 ```java
 public class ExemploBreakContinue {
    public static void main(String[] args) {
        for(int numero = 1; numero <=5; numero++) {
            if(numero == 3) break;
            System.out.println(numero);
        }
    }
}
 ```
Deve retornar 2.

```java
public class ExemploBreakContinue {
    public static void main(String[] args) {
        for(int numero = 1; numero <=5; numero++) {
            if(numero == 3) continue;
            System.out.println(numero);
        }
    }
}
```

Deve retornar 5.

##

### While

O laço `while` (na tradução literal "enquanto") determina que enquanto a condição for válida, o bloco de codígo será executado. O laço `while` testa a condição antes de executar o código, logo, caso a condição seja inválida no primeiro teste o bloco nem será executado.

A estrutura de sintaxe do controle de repetição `while` é exibida abaixo:

```java
// Estrutura de controle de fluxo while

while (expressão booleana de validação) {
    // Comando que será executado até que a expressão de validação torne-se falsa
}
```

Joãozinho recebeu R$50,00 de mesada e foi em uma loja de doces gastar todo o seu dinheiro, logo, enquanto o valor dos doces não igualar a R$50,00 ele foi adicionando itens no carrinho.

```java
import java.util.concurrent.ThreadLocalRandom;

public class ExemploWhile {

    public static void main(String[] args) {
        double mesada = 50.0;

        while (mesada > 0) {
            Double valorDoce = valorAleatorio();

            if (valorDoce > mesada) {
                valorDoce = mesada;
            }

            System.out.println("Doce do valor: " + valorDoce + " Adicionado no carrinho");
            mesada = mesada - valorDoce;

        }
        System.out.println("mesada: " + mesada);
        System.out.println("Joaozinho gastou toda sua mesada em doces!");
    }

    private static double valorAleatorio() {
        return ThreadLocalRandom.current().nextDouble(2, 8);
    }
}
```

Deve retornar Joaozinho gastou toda sua mesada em doces!.

##

### Do / While

O laço `Do / While` (na tradução literal "faça... enquanto"), assim como o laço while, considera que enquanto uma determinada condição for válida o bloco de código será executado. Entretanto, `Do / While` testa a condição após executar o código, sendo assim, mesmo que a condição seja considerada inválida no primeiro teste o bloco será executado pelo menos uma vez.

A estrutura de sintaxe do controle de repetição `Do / While` é exibida abaixo:

```java
// Estrutra do controle de fluxo

do {
// Comando que será executado até que a expressão de validação torne-se falsa
} while (expressão booleana de validação);
```

Joãozinho resolveu ligar para o seu amigo dizendo que se entupiu de tanto comer doces:

```java
import java.util.Random;

public class ExemploDoWhile {
    public static void main(String[] args) {
        System.out.println("Discando...");

        do {
            // Executa repetidamente até alguém atender
            System.out.println("Telefone tocando...");
        } while (tocando());

        System.out.println("Alô!!!");
    }

    private static boolean tocando() {
        boolean atendeu = new Random().nextInt(3)==1;
        System.out.println("Atendeu?" + atendeu);
        // Negando o ate parar de continuar tocando
        return ! atendeu;
    }
}
```
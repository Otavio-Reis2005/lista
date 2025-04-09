O que vamos aprender:
Como usar o JOptionPane para entrada e saída de dados.

Como transformar texto em números.

Como usar condições (if/else) para decidir qual operação realizar.

Como exibir o resultado final.

🛠️ Ferramentas que vamos usar:
Java

Biblioteca Swing (JOptionPane)

🔹 Passo 1: Importar a biblioteca Swing
java
Copiar
Editar
import javax.swing.JOptionPane;
Isso serve para que a gente possa usar as janelas (InputDialog e MessageDialog) que aparecem na tela para o usuário.

🔹 Passo 2: Criar a classe e o método principal
java
Copiar
Editar
public class CalculadoraSimples {
    public static void main(String[] args) {
        // Aqui vai o código da calculadora
    }
}
Toda aplicação Java começa com o main. É como a "porta de entrada" do programa.

🔹 Passo 3: Pedir dois números ao usuário
java
Copiar
Editar
String input1 = JOptionPane.showInputDialog("Digite o primeiro número:");
String input2 = JOptionPane.showInputDialog("Digite o segundo número:");
O showInputDialog mostra uma caixinha onde o usuário digita algo. O que ele digita é sempre um texto (String).

Agora precisamos transformar esse texto em número:

java
Copiar
Editar
double numero1 = Double.parseDouble(input1);
double numero2 = Double.parseDouble(input2);
Double.parseDouble() converte o texto para número com vírgula (double). Se fossem inteiros, usaríamos Integer.parseInt().

🔹 Passo 4: Perguntar a operação que ele quer fazer
java
Copiar
Editar
String operacao = JOptionPane.showInputDialog("Qual operação deseja? (+, -, *, /)");
Aqui o usuário escolhe a operação digitando o símbolo: +, -, * ou /.

🔹 Passo 5: Calcular com base na operação escolhida
java
Copiar
Editar
double resultado = 0;

if (operacao.equals("+")) {
    resultado = numero1 + numero2;
} else if (operacao.equals("-")) {
    resultado = numero1 - numero2;
} else if (operacao.equals("*")) {
    resultado = numero1 * numero2;
} else if (operacao.equals("/")) {
    if (numero2 != 0) {
        resultado = numero1 / numero2;
    } else {
        JOptionPane.showMessageDialog(null, "Não é possível dividir por zero!");
        return;
    }
} else {
    JOptionPane.showMessageDialog(null, "Operação inválida.");
    return;
}
Aqui usamos if para ver qual operação o usuário escolheu. Se ele digitar algo errado, mostramos uma mensagem e saímos do programa com return.

🔹 Passo 6: Mostrar o resultado final
java
Copiar
Editar
JOptionPane.showMessageDialog(null, "O resultado é: " + resultado);
Exibe uma caixinha com o resultado da conta.

✅ Código completo:
java
Copiar
Editar
import javax.swing.JOptionPane;

public class CalculadoraSimples {
    public static void main(String[] args) {
        String input1 = JOptionPane.showInputDialog("Digite o primeiro número:");
        String input2 = JOptionPane.showInputDialog("Digite o segundo número:");

        double numero1 = Double.parseDouble(input1);
        double numero2 = Double.parseDouble(input2);

        String operacao = JOptionPane.showInputDialog("Qual operação deseja? (+, -, *, /)");

        double resultado = 0;

        if (operacao.equals("+")) {
            resultado = numero1 + numero2;
        } else if (operacao.equals("-")) {
            resultado = numero1 - numero2;
        } else if (operacao.equals("*")) {
            resultado = numero1 * numero2;
        } else if (operacao.equals("/")) {
            if (numero2 != 0) {
                resultado = numero1 / numero2;
            } else {
                JOptionPane.showMessageDialog(null, "Não é possível dividir por zero!");
                return;
            }
        } else {
            JOptionPane.showMessageDialog(null, "Operação inválida.");
            return;
        }

        JOptionPane.showMessageDialog(null, "O resultado é: " + resultado);
    }
}

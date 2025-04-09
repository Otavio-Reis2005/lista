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



🎯 Objetivo do programa:
Simular um sistema de login, onde:

O usuário digita o nome de usuário e a senha.

O programa verifica se os dados estão corretos.

Se estiverem certos, mostra "Acesso permitido".

Se estiverem errados, deixa tentar de novo.

🧠 O que você vai aprender:
Usar JOptionPane.showInputDialog() para pegar dados do usuário.

Comparar textos com .equals().

Usar um laço de repetição (while) para continuar tentando até acertar.

🛠️ Ferramentas:
Java

Swing (JOptionPane)

🔹 Passo 1: Importar a biblioteca
java
Copiar
Editar
import javax.swing.JOptionPane;
Isso permite usar as janelinhas do JOptionPane.

🔹 Passo 2: Criar a classe e o método principal
java
Copiar
Editar
public class SistemaLogin {
    public static void main(String[] args) {
        // Aqui vamos programar o sistema de login
    }
}
Toda aplicação Java começa aqui.

🔹 Passo 3: Criar o laço de repetição
A ideia é repetir enquanto o usuário e senha estiverem incorretos.

java
Copiar
Editar
String usuarioCorreto = "admin";
String senhaCorreta = "1234";

boolean acessoPermitido = false;

while (!acessoPermitido) {
    String usuario = JOptionPane.showInputDialog("Digite o nome de usuário:");
    String senha = JOptionPane.showInputDialog("Digite a senha:");

    if (usuario.equals(usuarioCorreto) && senha.equals(senhaCorreta)) {
        JOptionPane.showMessageDialog(null, "Acesso permitido");
        acessoPermitido = true;
    } else {
        JOptionPane.showMessageDialog(null, "Usuário ou senha incorretos. Tente novamente.");
    }
}
✨ O que está acontecendo:
usuarioCorreto e senhaCorreta são os dados que queremos verificar.

Criamos uma variável booleana acessoPermitido que começa como false.

Usamos um while que só para quando acessoPermitido for true.

Se o usuário e a senha forem certos, mostramos "Acesso permitido" e saímos do laço.

Se estiverem errados, mostramos o erro e repetimos.


}
🧪 Teste o programa:
Rode ele e digite algo errado: ele vai repetir.

Digite admin e 1234: ele mostra "Acesso permitido" e para.


🎯 Objetivo:
Contar quantas vogais existem em uma palavra digitada pelo usuário.

🧠 O que vamos aprender:
Como percorrer cada letra de uma palavra (string).

Como comparar letras para saber se são vogais.

Como usar JOptionPane para entrada e saída.

Como incrementar um contador.

🛠️ Ferramentas:
Java

Swing (JOptionPane)

🔹 Passo 1: Importar a biblioteca
java
Copiar
Editar
import javax.swing.JOptionPane;
Permite usar janelinhas para interação com o usuário.

🔹 Passo 2: Criar a classe e o método principal
java
Copiar
Editar
public class ContadorVogais {
    public static void main(String[] args) {
        // Código vai aqui
    }
}
🔹 Passo 3: Pedir uma palavra ao usuário
java
Copiar
Editar
String palavra = JOptionPane.showInputDialog("Digite uma palavra:");
O que o usuário digitar será armazenado na variável palavra.

🔹 Passo 4: Contar as vogais
Vamos percorrer cada letra e verificar se é uma vogal.

java
Copiar
Editar
int contador = 0;
palavra = palavra.toLowerCase(); // Deixa tudo minúsculo para facilitar a comparação

for (int i = 0; i < palavra.length(); i++) {
    char letra = palavra.charAt(i); // Pega uma letra da palavra

    if (letra == 'a' || letra == 'e' || letra == 'i' || letra == 'o' || letra == 'u') {
        contador++;
    }
}
🔹 Passo 5: Mostrar o resultado
java
Copiar
Editar
JOptionPane.showMessageDialog(null, "A palavra contém " + contador + " vogais.");

 Objetivo:
O computador escolhe um número aleatório de 1 a 100, e o usuário tenta adivinhar até acertar. O jogo informa se o palpite está acima, abaixo ou correto, e conta quantas tentativas foram feitas.

🧠 O que você vai aprender:
Como gerar números aleatórios com Math.random().

Como converter String em int.

Como comparar números.

Como repetir até acertar usando while.

🛠️ Ferramentas:
Java

Swing (JOptionPane)

🔹 Passo 1: Importar a biblioteca
java
Copiar
Editar
import javax.swing.JOptionPane;
🔹 Passo 2: Criar a estrutura do programa
java
Copiar
Editar
public class JogoAdivinhacao {
    public static void main(String[] args) {
        // Código aqui
    }
}
🔹 Passo 3: Gerar um número aleatório entre 1 e 100
java
Copiar
Editar
int numeroSecreto = (int) (Math.random() * 100) + 1;
Math.random() gera um número entre 0.0 e 1.0. Multiplicamos por 100 e somamos 1 para garantir que o número vai de 1 até 100.
O (int) serve pra converter pra número inteiro.

🔹 Passo 4: Criar laço para o usuário tentar adivinhar
java
Copiar
Editar
int tentativa = 0;
int numeroUsuario = 0;

while (numeroUsuario != numeroSecreto) {
    String input = JOptionPane.showInputDialog("Adivinhe um número entre 1 e 100:");
    numeroUsuario = Integer.parseInt(input);
    tentativa++;

    if (numeroUsuario < numeroSecreto) {
        JOptionPane.showMessageDialog(null, "Tente um número maior.");
    } else if (numeroUsuario > numeroSecreto) {
        JOptionPane.showMessageDialog(null, "Tente um número menor.");
    } else {
        JOptionPane.showMessageDialog(null, "Parabéns! Você acertou em " + tentativa + " tentativas.");
    }
}

 Objetivo:
O usuário digita uma temperatura e escolhe se quer converter de Celsius para Fahrenheit ou o contrário (Fahrenheit para Celsius). O programa faz a conta e mostra o resultado.

🧠 O que vamos aprender:
Como ler número com JOptionPane.

Como converter texto para número com Double.parseDouble().

Como usar if para escolher o tipo de conversão.

Fórmulas de conversão de temperatura.

🛠️ Ferramentas:
Java

Swing (JOptionPane)

🔹 Fórmulas que vamos usar:
Celsius → Fahrenheit: F = (C × 9/5) + 32

Fahrenheit → Celsius: C = (F − 32) × 5/9

🔹 Passo 1: Importar biblioteca
java
Copiar
Editar
import javax.swing.JOptionPane;
🔹 Passo 2: Criar classe e método principal
java
Copiar
Editar
public class ConversorTemperatura {
    public static void main(String[] args) {
        // código aqui
    }
}
🔹 Passo 3: Ler a temperatura
java
Copiar
Editar
String inputTemp = JOptionPane.showInputDialog("Digite a temperatura:");
double temperatura = Double.parseDouble(inputTemp);
Aqui pegamos o valor como texto e depois transformamos em número com vírgula (double).

🔹 Passo 4: Perguntar o tipo de conversão
java
Copiar
Editar
String tipo = JOptionPane.showInputDialog("Deseja converter:\n1 - Celsius para Fahrenheit\n2 - Fahrenheit para Celsius");
O usuário digita "1" ou "2".

🔹 Passo 5: Fazer a conversão com base na escolha
java
Copiar
Editar
double resultado = 0;

if (tipo.equals("1")) {
    resultado = (temperatura * 9 / 5) + 32;
    JOptionPane.showMessageDialog(null, temperatura + "°C = " + resultado + "°F");
} else if (tipo.equals("2")) {
    resultado = (temperatura - 32) * 5 / 9;
    JOptionPane.showMessageDialog(null, temperatura + "°F = " + resultado + "°C");
} else {
    JOptionPane.showMessageDialog(null, "Opção inválida.");
}

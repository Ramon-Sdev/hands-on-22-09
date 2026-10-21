# hands-on-22-09
atividade da faculdade 
01 public class Ex01 {
    public static void main(String[] args) {
        int n = Entrada.lerInt("Digite um número inteiro: ");
        System.out.println(n % 2 == 0 ? "PAR" : "ÍMPAR");
    }
}

02 public class Ex02 {
    public static void main(String[] args) {
        int a = Entrada.lerInt("Primeiro número: ");
        int b = Entrada.lerInt("Segundo número: ");
        if (a == b) {
            System.out.println("Iguais");
        } else {
            System.out.println("Maior: " + Math.max(a, b));
        }
    }
}

03 public class Ex03 {
    public static void main(String[] args) {
        System.out.println("1- Somar");
        System.out.println("2- Subtrair");
        System.out.println("3- Multiplicar");
        System.out.println("4- Dividir");
        int opcao = Entrada.lerInt("Opção: ");
        if (opcao < 1 || opcao > 4) {
            System.out.println("Opção inválida.");
            return;
        }
        double a = Entrada.lerDouble("Primeiro número: ");
        double b = Entrada.lerDouble("Segundo número: ");

        switch (opcao) {
            case 1 -> System.out.println("Resultado = " + (a + b));
            case 2 -> System.out.println("Resultado = " + (a - b));
            case 3 -> System.out.println("Resultado = " + (a * b));
            case 4 -> {
                if (b == 0) {
                    System.out.println("Erro: divisão por zero não é permitida.");
                } else {
                    System.out.println("Resultado = " + (a / b));
                }
            }
        }
    }
}

04 public class Ex04 {
    public static void main(String[] args) {
        double nota;
        do {
            nota = Entrada.lerDouble("Digite uma nota entre 0 e 100: ");
            if (nota < 0 || nota > 100) {
                System.out.println("Nota inválida.");
            }
        } while (nota < 0 || nota > 100);
        System.out.println("Nota registrada: " + nota);
    }
}

05 public class Ex05 {
    public static void main(String[] args) {
        double saldo = 1000.00;
        int opcao;
        do {
            System.out.println();
            System.out.println("1- Depositar");
            System.out.println("2- Sacar");
            System.out.println("3- Ver saldo");
            System.out.println("4- Sair");
            opcao = Entrada.lerInt("Opção: ");

            switch (opcao) {
                case 1 -> {
                    double valor = Entrada.lerDouble("Valor do depósito: R$ ");
                    if (valor > 0) {
                        saldo += valor;
                        System.out.println("Depósito realizado.");
                    } else {
                        System.out.println("Depósito inválido: o valor deve ser maior que zero.");
                    }
                }
                case 2 -> {
                    double valor = Entrada.lerDouble("Valor do saque: R$ ");
                    if (valor <= 0) {
                        System.out.println("Saque inválido: o valor deve ser maior que zero.");
                    } else if (valor > saldo) {
                        System.out.println("Saldo insuficiente.");
                    } else {
                        saldo -= valor;
                        System.out.println("Saque realizado.");
                    }
                }
                case 3 -> System.out.printf("Saldo: R$ %.2f%n", saldo);
                case 4 -> System.out.printf("Saldo final: R$ %.2f%n", saldo);
                default -> System.out.println("Opção inválida.");
            }
        } while (opcao != 4);
    }
}

06 public class Ex06 {
    public static void main(String[] args) {
        double compra = Entrada.lerDouble("Valor da compra: R$ ");
        int categoria = Entrada.lerInt("Categoria (1 = comum, 2 = premium, 3 = funcionário): ");

        double percentual;
        switch (categoria) {
            case 1 -> percentual = 0.05;
            case 2 -> percentual = 0.10;
            case 3 -> percentual = 0.15;
            default -> {
                System.out.println("Categoria inválida");
                return;
            }
        }
        double desconto = compra * percentual;
        System.out.printf("Desconto: R$ %.2f%n", desconto);
        System.out.printf("Valor final a pagar: R$ %.2f%n", compra - desconto);
    }
}

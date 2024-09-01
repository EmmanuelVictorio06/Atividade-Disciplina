import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class GestaoAcademica {
    private List<Aluno> alunos;
    private List<Disciplina> disciplinas;
    private Scanner scanner;

    // Construtor
    public GestaoAcademica() {
        alunos = new ArrayList<>();
        disciplinas = new ArrayList<>();
        scanner = new Scanner(System.in);
    }

    // Método principal
    public static void main(String[] args) {
        GestaoAcademica sistema = new GestaoAcademica();
        sistema.exibirMenu();
    }

    // Exibir Menu
    private void exibirMenu() {
        int opcao = -1;
        while (opcao != 7) {
            System.out.println("\n--- Menu de Opções ---");
            System.out.println("1. Matricular Alunos");
            System.out.println("2. Listar Disciplinas");
            System.out.println("3. Listar Alunos (por disciplina)");
            System.out.println("4. Pesquisar Disciplina (por nome ou por código)");
            System.out.println("5. Pesquisar Aluno (por nome ou matrícula)");
            System.out.println("6. Alterar informações do estudante");
            System.out.println("7. Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();
            scanner.nextLine(); // Consumir nova linha

            switch (opcao) {
                case 1:
                    matricularAluno();
                    break;
                case 2:
                    listarDisciplinas();
                    break;
                case 3:
                    listarAlunosPorDisciplina();
                    break;
                case 4:
                    pesquisarDisciplina();
                    break;
                case 5:
                    pesquisarAluno();
                    break;
                case 6:
                    alterarInformacoesEstudante();
                    break;
                case 7:
                    System.out.println("Saindo...");
                    break;
                default:
                    System.out.println("Opção inválida. Tente novamente.");
            }
        }
    }

    // Implementação das funcionalidades do menu
    private void matricularAluno() {
        System.out.print("Nome do Aluno: ");
        String nome = scanner.nextLine();
        System.out.print("Matrícula do Aluno: ");
        String matricula = scanner.nextLine();
        Aluno aluno = new Aluno(nome, matricula);
        alunos.add(aluno);
        System.out.println("Aluno matriculado com sucesso!");

        // Assumindo que queremos matricular o aluno em uma disciplina específica
        System.out.print("Código da Disciplina: ");
        String codigoDisciplina = scanner.nextLine();

        // Buscando disciplina diretamente dentro do método
        Disciplina disciplina = null;
        for (Disciplina d : disciplinas) {
            if (d.getCodigo().equalsIgnoreCase(codigoDisciplina)) {
                disciplina = d;
                break;
            }
        }

        if (disciplina != null) {
            disciplina.matricularAluno(aluno);
            System.out.println("Aluno matriculado na disciplina com sucesso!");
        } else {
            System.out.println("Disciplina não encontrada.");
        }
    }

    private void listarDisciplinas() {
        if (disciplinas.isEmpty()) {
            System.out.println("Nenhuma disciplina cadastrada.");
        } else {
            for (Disciplina disciplina : disciplinas) {
                System.out.println(disciplina);
            }
        }
    }

    private void listarAlunosPorDisciplina() {
        System.out.print("Código da Disciplina: ");
        String codigoDisciplina = scanner.nextLine();

        // Buscando disciplina diretamente dentro do método
        Disciplina disciplina = null;
        for (Disciplina d : disciplinas) {
            if (d.getCodigo().equalsIgnoreCase(codigoDisciplina)) {
                disciplina = d;
                break;
            }
        }

        if (disciplina != null) {
            List<Aluno> alunos = disciplina.getAlunosMatriculados();
            if (alunos.isEmpty()) {
                System.out.println("Nenhum aluno matriculado nesta disciplina.");
            } else {
                for (Aluno aluno : alunos) {
                    System.out.println(aluno);
                }
            }
        } else {
            System.out.println("Disciplina não encontrada.");
        }
    }

    private void pesquisarDisciplina() {
        System.out.print("Digite o nome ou o código da disciplina: ");
        String input = scanner.nextLine();

        // Buscando disciplina diretamente dentro do método
        Disciplina disciplina = null;
        for (Disciplina d : disciplinas) {
            if (d.getNome().equalsIgnoreCase(input) || d.getCodigo().equalsIgnoreCase(input)) {
                disciplina = d;
                break;
            }
        }

        if (disciplina != null) {
            System.out.println(disciplina);
        } else {
            System.out.println("Disciplina não encontrada.");
        }
    }

    private void pesquisarAluno() {
        System.out.print("Digite o nome ou a matrícula do aluno: ");
        String input = scanner.nextLine();

        // Buscando aluno diretamente dentro do método
        Aluno aluno = null;
        for (Aluno a : alunos) {
            if (a.getNome().equalsIgnoreCase(input) || a.getMatricula().equalsIgnoreCase(input)) {
                aluno = a;
                break;
            }
        }

        if (aluno != null) {
            System.out.println(aluno);
        } else {
            System.out.println("Aluno não encontrado.");
        }
    }

    private void alterarInformacoesEstudante() {
        System.out.print("Digite a matrícula do aluno que deseja alterar: ");
        String matricula = scanner.nextLine();

        // Buscando aluno diretamente dentro do método
        Aluno aluno = null;
        for (Aluno a : alunos) {
            if (a.getMatricula().equalsIgnoreCase(matricula)) {
                aluno = a;
                break;
            }
        }

        if (aluno != null) {
            System.out.print("Novo nome do Aluno: ");
            String novoNome = scanner.nextLine();
            aluno.setNome(novoNome);
            System.out.println("Informações do aluno alteradas com sucesso!");
        } else {
            System.out.println("Aluno não encontrado.");
        }
    }
}

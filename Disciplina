import java.util.ArrayList;
import java.util.List;

public class Disciplina {
    private String nome;
    private String codigo;
    private List<Aluno> alunosMatriculados;

    // Construtor
    public Disciplina(String nome, String codigo) {
        this.nome = nome;
        this.codigo = codigo;
        this.alunosMatriculados = new ArrayList<>();
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getCodigo() {
        return codigo;
    }

    public void setCodigo(String codigo) {
        this.codigo = codigo;
    }

    public List<Aluno> getAlunosMatriculados() {
        return alunosMatriculados;
    }

    public void matricularAluno(Aluno aluno) {
        alunosMatriculados.add(aluno);
    }

    @Override
    public String toString() {
        return "Disciplina{" +
                "nome='" + nome + '\'' +
                ", codigo='" + codigo + '\'' +
                ", alunosMatriculados=" + alunosMatriculados +
                '}';
    }
}

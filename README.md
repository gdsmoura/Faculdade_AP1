// Classe abstrata Veiculo
abstract class Veiculo {
    public String marca;
    public String modelo;
    private int ano;

    // Método abstrato para retornar informações sobre o veículo
    public abstract String informacoesVeiculo();

    // Método para acessar o atributo ano
    public int getAno() {
        return ano;
    }

    // Método para modificar o atributo ano
    public void setAno(int ano) {
        this.ano = ano;
    }
}

// Classe Carro que herda de Veiculo
class Carro extends Veiculo {
    public int numeroPortas;

    // Implementação do método abstrato para informar os dados do veículo
    @Override
    public String informacoesVeiculo() {
        return "Carro: Marca: " + marca + ", Modelo: " + modelo + ", Ano: " + getAno() + ", Número de Portas: " + numeroPortas;
    }
}

// Classe Moto que herda de Veiculo
class Moto extends Veiculo {
    private int cilindrada;

    // Implementação do método abstrato para informar os dados do veículo
    @Override
    public String informacoesVeiculo() {
        return "Moto: Marca: " + marca + ", Modelo: " + modelo + ", Ano: " + getAno() + ", Cilindrada: " + cilindrada;
    }

    // Método para acessar o atributo cilindrada
    public int getCilindrada() {
        return cilindrada;
    }

    // Método para modificar o atributo cilindrada
    public void setCilindrada(int cilindrada) {
        this.cilindrada = cilindrada;
    }
}

// Classe Main para testar as implementações
public class Main {
    public static void main(String[] args) {
        // Instanciando um objeto Carro
        Carro carro = new Carro();
        carro.marca = "Toyota";
        carro.modelo = "Corolla";
        carro.setAno(2020);
        carro.numeroPortas = 4;

        // Instanciando um objeto Moto
        Moto moto = new Moto();
        moto.marca = "Honda";
        moto.modelo = "CB500";
        moto.setAno(2022);
        moto.setCilindrada(500);

        // Imprimindo as informações dos veículos
        System.out.println(carro.informacoesVeiculo());
        System.out.println(moto.informacoesVeiculo());
    }
}

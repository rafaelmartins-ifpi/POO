## Exercício 01 - Respostas

[**1. Qual a diferença entre objetos e classes? Exemplifique.**]("color: blue")

**Classe** é algo abstrato, lógico. Onde estão definidos todos os elementos e características. A classe tipifica o que será modelado por ela. Ela determina os estados possíveis e os comportamentos que os objetos podem ter. 

**Objeto** é algo concreto, físico. Nele os elementos estão de fato presentes. É algo palpável, que pode ser manipulado. Ele existe na memória, durante a execução da aplicação. O objeto possui valores para os estados definidos e chamam os comportamentos definidos executando os algoritmos. Tem um tempo de vida transitório.

Assim, o objeto é uma instância da classe. Na classe você pode dizer que aquele objeto terá uma cor, no objeto você diz qual é a cor, só pode dizer isso porque foi definido na classe que essa informação deve estar no objeto.

Exemplificação: Planta (classe) – Casa construída (objeto)

<br/>

**2. De forma breve, conceitue atributos e métodos. Pesquise e exemplifique um exemplo de objeto que possua atributos e métodos (notação livre).**

**Atributos** são as características de um objeto, essas características também são conhecidas como variáveis, utilizando o exemplo dos cães, temos alguns atributos, tais como: cor, peso, altura e nome.

**Métodos** são as ações que os objetos podem exercer quando solicitados, onde podem interagir e se comunicarem com outros objetos, utilizando o exemplo dos cães, temos alguns exemplos: latir, correr, pular.

<br/>

**3. A abstração visa focar no que é importante para um sistema. Você concorda que um atributo de uma pessoa pode ser importante ou não dependendo do contexto do sistema. Enumere na tabela abaixo contextos/sistemas distintos em que os atributos abaixo seriam relevantes:**

Atributo | Sistema em que não é importante | Sistema em que é mais ou menos importante | Sistema em que é importante
:------: | :------: | :------: | :------:
Peso | Detran | Vacina | Academia
Tipo Sanguíneo | Biblioteca | Escola | Hospital
Raça | Banco | Futebol | Concurso

<br/>

 **4. Considerando os objetos Pessoa e Conta:**

**a. Seria interessante em um sistema bancário um objeto "conta" possuir uma "pessoa" como um atributo interno representando o titular da conta?**  

Sim. Para saber o titular daquela conta específica.

<br/>

**b. Olhando no sentido inverso, seria interessante uma pessoa possuir mais de uma conta como atributo? Que elemento da programação estruturada melhor representaria o conjunto de contas de uma pessoa?** 
 
Sim. Pois uma pessoa pode ser titular de mais de uma conta. 
Nesse caso, poderia ser modelado um atributo contendo o conjunto de contas pertencentes àquela pessoa, com a utilização de “lista”, “array”, “vetor”.

<br/>

**5. Identifique pelo menos 5 objetos de um sistema de controle acadêmico. Ex: aluno.**

Professor, Notas, Disciplina, Aluno, Curso etc.

<br/>

**6. Imagine um jogo qualquer. Identifique o máximo de objetos possíveis e eventuais características (atributos) e comportamentos (métodos) que os mesmos poderiam ter.**

Objeto | Atributos | Métodos
:-----: | :-----: | :-----:
Jogador | peso, altura, força, velocidade | chutar, correr, efetuar passe
Árbitro | nacionalidade, resitência, experiência | acompanhar lance, marcar falta, aplica cartões
Clube | bandeira, hino, cores, arrecadação, gastos, jogadores | comprar e vender jogadores, realizar transações 

<br/>

**7. Considerando o exemplo da classe Retangulo dos slides, implemente um método adicional chamado que calcule o perímetro do retângulo. Teste os métodos do retângulo.**

~~~TypeScript
class Retangulo {
    lado1: number = 0;
    lado2: number = 0;

    calcularArea(): number {
        return this.l1 * this.l2;
    
    calcularPerimetro(): number {
        return (this.lado1 + this.lado2)*2;
    }
}

let r1: Retangulo = new Retangulo();
r1.lado1 = 4;
r1.lado2 = 8;
console.log(r1);
r1.exibirPerimetro();
~~~

<br/>

**8. Crie uma classe Circulo que possua um atributo raio. Crie dois métodos que calculam a área e o perímetro. Instancie um objeto dessa classe, atribua um valor ao raio e exiba a área e o perímetro chamando os dois métodos definidos.**

~~~TypeScript
class Circulo {
    raio: number = 0;
    
    calcularArea() {
        return 3.1415 * this.raio * this.raio;
    }

    calcularPerimetro() {
        return 2 * 3.1415 * this.raio;
    }
}

let c1: Circulo = new Circulo();
c1.raio = 4;

concole.log (`Área: ${c1.exibirArea()}`);
console.log (`Perímetro: ${c1.exibirPerimetro()}`);
~~~

<br/>

**9. Crie uma classe chamada SituacaoFinanceira com os atributos valorCreditos e valorDebitos. Crie um método chamado calcularSaldo() que retorna/calcula a diferença entre crédito e débito. Instancie uma classe SituacaoFinanceira, inicialize os dois atributos e exiba o resultado do método calcularSaldo().**

~~~TypeScript
class SituacaoFinanceira {
    valorCreditos: number = 0;
    valorDebitos: number = 0;

    calcularSaldo() {
        return this.valorCreditos - this.valorDebitos;
    }
}

let pessoa: SituacaoFinanceira = new SituacaoFinanceira();
pessoa.valorCreditos = 5678.63;
pessoa.valorDebitos = 2365.78;

console.log (`O Saldo é: ${pessoa.saldo()}`);
~~~

<br/>

**10. Represente as classes das questões 8 e 9 no formato UML. Pesquise uma ferramenta on line.** 

Circulo
:-----:
raio:number
calcularArea()<br/>calcularPerimetro()

SituaçãoFinanceira
:-----:
valorCreditos: number<br/>valorDebitos: number
calcularSaldo()


## Exercício 01 - Respostas

### 1. Qual a diferença entre objetos e classes? Exemplifique.

**Classe** é algo abstrato, lógico. Onde estão definidos todos os elementos e características. A classe tipifica o que será modelado por ela. Ela determina os estados possíveis e os comportamentos que os objetos podem ter. 

**Objeto** é algo concreto, físico. Nele os elementos estão de fato presentes. É algo palpável, que pode ser manipulado. Ele existe na memória, durante a execução da aplicação. O objeto possui valores para os estados definidos e chamam os comportamentos definidos executando os algoritmos. Tem um tempo de vida transitório.

Assim, o objeto é uma instância da classe. Na classe você pode dizer que aquele objeto terá uma cor, no objeto você diz qual é a cor, só pode dizer isso porque foi definido na classe que essa informação deve estar no objeto.

Exemplificação: Planta (classe) – Casa construída (objeto)  

<br/>

### 2. De forma breve, conceitue atributos e métodos. Pesquise e exemplifique um exemplo de objeto que possua atributos e métodos (notação livre).

**Atributos** são as características de um objeto, essas características também são conhecidas como variáveis, utilizando o exemplo dos cães, temos alguns atributos, tais como: cor, peso, altura e nome.

**Métodos** são as ações que os objetos podem exercer quando solicitados, onde podem interagir e se comunicarem com outros objetos, utilizando o exemplo dos cães, temos alguns exemplos: latir, correr, pular.

<br/>

### 3. A abstração visa focar no que é importante para um sistema. Você concorda que um atributo de uma sf pode ser importante ou não dependendo do contexto do sistema. Enumere na tabela abaixo contextos/sistemas distintos em que os atributos abaixo seriam relevantes:

Atributo | Sistema em que não é importante | Sistema em que é mais ou menos importante | Sistema em que é importante
:------: | :------: | :------: | :------:
Peso | Detran, Biblioteca | Estoque | Academia, Nutrição
Tipo de CNH | Acadêmico, Escolinha de Futebol, Rede Social | Exército, Cadastro Civil no Geral | Detran, Locadora de Veículos, empresa de ônibus
Tipo Sanguíneo | Bancário, Estoque | Concurso, Educacional | Emopi, Hospitalar, Exército
Habilidade Destra | Acadêmico | Escola de Música| Controle Desportivo (futebol, tênis)  
Percentual de Gordura | Bancário, Rede Social | Teste de aptidão física | Academia, Hospitalar
Saldo em conta | Acadêmico, EMOPI | rede Social | Jogos, Bancário, Venda
Etinia | Ifood, entregas, comércio eletrônico | Rede Social | Censo Demográfico, Processo Seletivo

<br/>

### 4. Considerando os objetos sf e Conta:

### a. Seria interessante em um sistema bancário um objeto "conta" possuir uma "sf" como um atributo interno representando o titular da conta?

Sim. Para saber o titular daquela conta específica.

<br/>

### b. Olhando no sentido inverso, seria interessante uma sf possuir mais de uma conta como atributo? Que elemento da programação estruturada melhor representaria o conjunto de contas de uma sf? 
 
Sim. Pois uma sf pode ser titular de mais de uma conta. 
Nesse caso, poderia ser modelado um atributo contendo o conjunto de contas pertencentes àquela sf, com a utilização de  “array”.

<br/>

### 5. Identifique pelo menos 5 objetos de um sistema de controle acadêmico. Ex: aluno.

Professor, Turma, Disciplina, Coordenador, Aluno, Sala etc.

<br/>

### 6. Imagine um jogo qualquer. Identifique o máximo de objetos possíveis e eventuais características (atributos) e comportamentos (métodos) que os mesmos poderiam ter.

Objeto | Atributos | Métodos
:-----: | :-----: | :-----:
Jogador | peso, altura, força, velocidade | chutar, correr, efetuar passe
Árbitro | nacionalidade, resitência, experiência | acompanhar lance, marcar falta, aplica cartões
Clube | bandeira, hino, cores, arrecadação, gastos, jogadores | comprar e vender jogadores, realizar transações 

<br/>

### 7. Considerando o exemplo da classe Retangulo dos slides, implemente um método adicional chamado que calcule o perímetro do retângulo. Teste os métodos do retângulo.

~~~TypeScript
class Retangulo {
    l1: number = 0;
    l2: number = 0;

    calcularArea(): number {
        return this.l1 * this.l2;
    }
    
    calcularPerimetro(): number {
        return (this.l1 + this.l2)*2;
    }
}

let r: Retangulo = new Retangulo();
r.l1 = 4;
r.l2 = 8;
console.log(r.calcularPerimetro());
~~~

<br/>

### 8. Crie uma classe Circulo que possua um atributo raio. Crie dois métodos que calculam a área e o perímetro. Instancie um objeto dessa classe, atribua um valor ao raio e exiba a área e o perímetro chamando os dois métodos definidos.

~~~TypeScript
class Circulo {
    raio: number = 0;
    pi: number = 3.1415;
    
    calcularArea(): number {
        return this.pi * this.raio * this.raio;
    }

    calcularPerimetro(): number {
        return 2 * this.pi * this.raio;
    }
}

let c: Circulo = new Circulo();
c.raio = 4;

console.log (`Área: ${c.calcularArea()}`);
console.log (`Perímetro: ${c.calcularPerimetro()}`);
~~~

<br/>

### 9. Crie uma classe chamada SituacaoFinanceira com os atributos valorCreditos e valorDebitos. Crie um método chamado calcularSaldo() que retorna/calcula a diferença entre crédito e débito. Instancie uma classe SituacaoFinanceira, inicialize os dois atributos e exiba o resultado do método calcularSaldo().

~~~TypeScript
class SituacaoFinanceira {
    valorCreditos: number = 0;
    valorDebitos: number = 0;

    calcularSaldo() {
        return this.valorCreditos - this.valorDebitos;
    }
}

let sf: SituacaoFinanceira = new SituacaoFinanceira();
sf.valorCreditos = 250.50;
sf.valorDebitos = 100.50;

console.log (`O Saldo é: ${sf.calcularSaldo()}`);
~~~

<br/>

### 10. Represente as classes das questões 8 e 9 no formato UML. Pesquise uma ferramenta on line.

Sugestões de Ferramentas: draw.io, plantuml, lucidchart


|**Circulo**|
:-----:
raio:number
calcularArea()<br>calcularPerimetro()

<br>

|**SituaçãoFinanceira**|
:-----:
valorCreditos: number<br/>valorDebitos: number
calcularSaldo()

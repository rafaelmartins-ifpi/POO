### Questão 1.  

~~~typescript
class Empregado {
    
    salario: number = 500;

    calcularSalario (): number {
        return this.salario;
    }
}


class Diarista extends Empregado {

    override calcularSalario (): number {
        return this.salario/30;
    }
}


class Horista extends Diarista {

    override calcularSalario(): number {
        return this.salario/24;    
    }
}
~~~

<br>

### Questão 2.
~~~typescript
class Pessoa {

    private _nome: string;
    private _sobrenome: string;

    constructor (nome: string, sobrenome: string){
        this._nome = nome;
        this._sobrenome = sobrenome;
    }

    get nome (): string {
        return this._nome;
    }
    
    get sobrenome (): string {
        return this._sobrenome;
    }

    get nomeCompleto (): string {
        return this._nome + " " + this._sobrenome;
    }
}
~~~

<br>  

### Questão 3.

~~~typescript 
class Funcionario extends Pessoa {

    private _matricula: string;
    private _salario: number;

    constructor (nome: string, sobrenome: string, matricula: string, salario: number) {
        super (nome, sobrenome);
        this._matricula = matricula;
        this._salario = salario;
    }

    get matricula (): string {
        return this._matricula;
    }

    get salario (): number {
        return this._salario;
    }

    calcularSalarioPrimeiraParcela (): number {
        return 0.6 * this._salario;
    }

    calcularSalarioSegundaParcela (): number {
        return 0.4 * this._salario;
    }
}
~~~

<br>

### Questão 4.
~~~typescript
class Professor extends Funcionario {

    private _titulacao: string;

    constructor (nome: string, sobrenome: string, matricula: string, salario: number, titulacao: string){
        super (nome, sobrenome, matricula,salario);
        this._titulacao = titulacao;
    }

    get titulacao (): string {
        return this._titulacao;
    }

    override calcularSalarioPrimeiraParcela(): number {
        return this.salario;
    }

    override calcularSalarioSegundaParcela(): number {
        return 0;
    }
}
~~~

<br>

### Questão 5. 
~~~typescript 
class FolhaPagamento {
    
    folha: Pessoa[];
   
    constructor (folha: Pessoa[]) {
        this.folha = folha;
    }

    calcularPagamentos (): number {
        let totalSalarios: number = 0;

        for (let i = 0; i < this.folha.length; i++) {
            if (this.folha[i] instanceof Funcionario){
                totalSalarios += (<Funcionario> this.folha[i]).salario;
            }
        }

        return totalSalarios;
    }
}

let pessoa1: Funcionario = new Funcionario("Fulano", "de tal", "1234", 1000);
let pessoa2: Professor = new Professor("Cicrano", "de tal", "1234", 1000, "mestre");
let pessoa3: Pessoa = new Pessoa("Amado", "Batista");
let pessoa4: Professor = new Professor("Wanderlei", "Andrade", "1234", 1000, "doutora");

let folha: Pessoa[] = [pessoa1, pessoa2, pessoa3, pessoa4];

let folhaPagamento: FolhaPagamento = new FolhaPagamento(folha);

console.log("Total de Salários: R$ " + folhaPagamento.calcularPagamentos());
~~~


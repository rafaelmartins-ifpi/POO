### Questão 1  

~~~typescript  
class Veiculo {
    placa: string;
    ano: number;
    
    constructor(placa: string, ano: number){
        this.placa = placa;
        this.ano = ano;
    }
}

class Carro extends Veiculo {
    modelo: string;

    constructor(placa: string, ano: number, modelo: string){
        super(placa, ano);
        this.modelo = modelo;
    }
}

class CarroEletrico extends Carro {
    autonomiaBateria: number;

    constructor(placa: string, ano: number, modelo: string, autonomiaBateria: number){
        super(placa, ano, modelo);
        this.autonomiaBateria = autonomiaBateria;
    }
}
~~~

<br>

### 2 Crie uma classe Calculadora com:  
#### a. Dois tributos privados chamados representando dois operandos;  
#### b. Crie um construtor que inicializa os atributos;  
#### c. Crie um método que retorna a soma dos dois atributos;  
#### d. Teste a classe.  
  
~~~typescript
class Calculadora {
    
    private _numero1: number;
    private _numero2: number;

    constructor (numero1: number, numero2: number){
        this._numero1 = numero1;
        this._numero2 = numero2;
    }

    somar(): number {
        return this._numero1 + this._numero2
    }    

}

let calculadora: Calculadora = new Calculadora(25, 75);
console.log(calculadora.somar());  //100
~~~
<br>

### 3. Crie uma classe chamada CalculadoraCientifica que herda da classe Calculadora do exercício passado e:
#### a. Implemente um método chamado exponenciar que retorne o primeiro operando elevado ao segundo;  
#### b. Teste a classe;  
#### c. Foi necessária alguma modificação em Calculadora para o acesso aos atributos? 

Sim, foi preciso alterar os atributos da classe Calculadora, de ***private*** para ***protected***

<br>

~~~typescript
class CalculadoraCientifica extends Calculadora {

    constructor (numero1: number, numero2: number){
        super (numero1, numero2);
    } 

    exponenciar(): number {
        return this._numero1 ** this._numero2;
    }

}

let calculadoraCientifica: CalculadoraCientifica = new CalculadoraCientifica (3, 3);
console.log (calculadoraCientifica.exponenciar());
~~~




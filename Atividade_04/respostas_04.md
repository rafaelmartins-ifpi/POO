### Questão 1. Assinale verdadeiro ou falso: 
#### ( F )  Objetos são modelos para classes;  
*Na programação orientada a objetos, classes são modelos para criar objetos, e não o contrário*  

#### ( F ) Atributos de uma classe devem ser obrigatoriamente inicializados para que as classes compilem;  
*Nem sempre é obrigatório inicializar os atributos de uma classe para que a classe compile.Isso depende da linguagem de programação.*

#### ( F ) Uma variável declarada dentro de um método deve ser inicializada para que a classe seja compilável;  
*A maioria das linguagens de programação permite declarar variáveis locais sem inicializá-las imediatamente*

#### ( F ) Uma variável que seja uma classe declarada em um método é automaticamente inicializada com undefined;  
*Depende da linguagem. Em java e C#, a variável declarada dentro de um método não é automaticamente inicializada com undefined. Ela é considerada como não inicializada até que seja explicitamente atribuída a um valor.  
Porém, em JavaScript e TypeScript,  uma variável declarada com let ou var dentro de um método ou função será inicializada com undefined se não for atribuído nenhum valor no momento da declaração*

#### ( V )  Construtores  são  rotinas  especiais  que  servem  para inicializar  e  configurar  os objetos no momento da instanciação;  

#### ( V ) Construtores não possuem tipo de retorno e podem ou não ter parâmetros;  

#### ( V )  Uma classe pode ter várias nstâncias  

<br>

### Questão 2.  
SIM. Em TypeScript, ao declarar uma variável de instância como quantReservas sem inicializá-la, 
o compilador espera que essa variável seja inicializada antes de qualquer operação que dependa do seu valor. 
Como quantReservas é do tipo number, e não foi atribuída a um valor inicial no código fornecido, o compilador 
não sabe com certeza qual é o valor de quantReservas no momento em que o método adicionarReserva() tenta incrementá-la.  
<br>

### Questão 3.  
~~~typescript
class Hotel { 
    
    quantReservas: number;
    
    constructor (quantReservas: number){
        this.quantReservas = quantReservas;
    }
    adicionarReserva() : void  { 
        this.quantReservas++; 
    } 
}

let hotel : Hotel = new Hotel(2); 
console.log(hotel.quantReservas);
~~~
<br>

### Questão 4.  
O erro ocorre porque o construtor da classe Radio exige um parâmetro volume, 
mas a instância é criada sem fornecer esse parâmetro.

Soluções: 
1. Passar o parâmetro ao criar a instância;
2. Tornar o parâmetro do construtor opcional ou fornecer um valor padrão.  
<br>  

### Questão 5.
#### a)
O resultado de todos os prints serã 90. Pois, tanto c1 e c3 apontam para o mesmo objeto de c2.  
Assim, como o saldo inicial era de 100 e houve um saque, o saldo será 90.  
A transferência de 50 não altera o saldo, pois as contas fazem refereência ao mesmo objeto.  

#### b)  
Os objetos inicialmente instanciados em c1 e c3 serão destruídos pelo GB - Garbage Collector.
Pois tornaram-se objetos sem referência (que não possuem mais variáveis apontando), já que c1 2 c3 
passaram a apontar para c2.  
<br>  

### Questão 6.  
~~~typescript
class Saudacao {
    texto: string;
    destinatario: string;

    constructor (texto: string, nome: string){
        this.texto = texto;
        this.destinatario = nome;
    }

    obterSaudacao(){
        return this.texto + ", " + this.destinatario;
    }
}

let saudacao1: Saudacao = new Saudacao("Boa tarde", "Prof. Ely Miranda");
console.log(saudacao1.obterSaudacao());
~~~
<br>

### Questão 7.  
~~~typescript
class Triangulo {
    lado1 : number;
    lado2 : number;
    lado3 : number;

    constructor (lado1:number, lado2:number, lado3:number){
        this.lado1 = lado1;
        this.lado2 = lado2;
        this.lado3 = lado3;
    }

    ehTriangulo (){
        if ((Math.abs(this.lado2 - this.lado3) < this.lado1) && (this.lado1 < (this.lado2 + this.lado3))){
            return true;
        }
        return false;
    }

    ehIsoceles (){
        if (!this.ehTriangulo()){
            return false;
        }

        if (this.ehEquilatero()){
            return false;
        }

        if ((this.lado1 === this.lado2) || (this.lado1 === this.lado3) || (this.lado2 === this.lado3)){
            return true;
        }
        
        return false;
    }

    ehEquilatero (){
        if (!this.ehTriangulo()){
            return false;
        }

        if ((this.lado1 === this.lado2) && (this.lado1 === this.lado3)){
            return true;
        }
        
        return false;
    }

    ehEscaleno (){
        if (!this.ehTriangulo()){
            return false;
        }

        if ((this.lado1 !== this.lado2) && (this.lado1 !== this.lado3) && (this.lado2 !== this.lado3)){
            return true;
        }
        
        return false;
    }
}

let triangulo1: Triangulo = new Triangulo(2,4,3);
console.log(triangulo1.ehEscaleno());
~~~
<br>

### Questão 8.  
~~~typescript
class Equipamento{
    ligado: boolean;

    constructor (ligado:boolean){
        this.ligado = ligado;
    }

    liga(){
        if (!this.ligado){
            this.ligado = true;
        }
    }

    desliga(){
        if(this.ligado){
            this.ligado = false;
        }
    }

    inverte(){
        this.ligado = !this.ligado;
    }

    estaLigado(){
        return this.ligado;
    }
}

let tomada: Equipamento = new Equipamento(false);
tomada.liga()
console.log(tomada.ligado);
tomada.inverte();
console.log(tomada.ligado);
~~~
<br>

### Questão 9.  
~~~typescript
class Conta {
    numero: String;
    saldo: number;

    constructor(numero: String, saldo: number) {
        this.numero = numero;
        this.saldo = saldo;
    }

    sacar(valor: number): boolean {
        if (valor <= this.saldo){
            this.saldo = this.saldo - valor;
            return true;            
        }

        return false;        
    }

    depositar(valor: number): void {
        this.saldo = this.saldo + valor;
    }

    consultarSaldo(): number {
        return this.saldo;
    }

    transferir(contaDestino: Conta, valor: number): boolean {
        if (this.sacar(valor)){
            this.sacar(valor);
            contaDestino.depositar(valor);
            return true
        }

        return false;        
    }
}

let c1: Conta = new Conta("1",100);
let c2: Conta = new Conta("2",50);

console.log(c1.transferir(c2,200));
console.log(c1.saldo);
console.log(c2.saldo);
~~~
<br>

### Questão 10.  
~~~typescript
class Jogador {
    forca: number;
    nivel: number;
    pontosAtuais: number;

    constructor(forca: number, nivel: number, pontosAtuais: number){
        this.forca = forca;
        this.nivel = nivel;
        this.pontosAtuais = pontosAtuais;
    }

    calcularAtaque(): number{
        return this.forca * this.nivel;
    }

    atacar (jogadorAtacado: Jogador): void {
        if (jogadorAtacado.estaVivo()) {
            jogadorAtacado.pontosAtuais = jogadorAtacado.pontosAtuais - this.calcularAtaque();
        }
    }

    estaVivo(): boolean{
        if (this.pontosAtuais > 0){
            return true;
        }
        return false;
    }

    toString(): string{
        return `Força: ${this.forca} \n Nível: ${this.nivel} \n Pontos: ${this.pontosAtuais}`
    }
}

let j1: Jogador = new Jogador(200,1,100);
let j2: Jogador = new Jogador(20,2,100);

console.log(j1.toString());
console.log(j2.toString());

j1.atacar(j2);

console.log(j1.toString());
console.log(j2.toString());
~~~
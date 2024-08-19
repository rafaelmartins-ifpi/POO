## Respostas - Exercício 01 - Extra

### 1. Identifique o nome do conceito representado pelo texto abaixo:
### a. É a forma de definir ou controlar a complexidade baseada em características essenciais e pela supressão ou desconsideração de detalhes em orientação a objetos 

Abstração

<br>

### b. Define  que  nenhum  acesso  direto  é  concedido  diretamente  aos  dados, apenas através de métodos.

Encapsulamento

<br>

### c. É um recurso que serve para inicializar os atributos e é executado automaticamente sempre que um novo objeto é criado.

Construtor

<br>

### 2. Assinale V ou F:

( F ) Classes são instâncias de objetos;

( F ) Classes são apenas agrupamentos de métodos;

( V ) Atributos definem o estado de um objeto;

( F ) Métodos podem ser análogos às funções e em TypeScript e podem ser escritos dentro ou fora da classe, como em C++;

( F ) Podemos ignorar o uso de tipos em TypeScript.

<br>

### 3. Considere os elementos e assinale a alternativa correta: Teresina Equipamentos Hidráulicos, Empresa e Nome da Empresa. Na orientação a objetos, os itens acima representam, respectivamente: 

- [ ] a. atributo, classe e objeto  
- [ ] b. classe, atributo e objeto  
- [ ] c. classe, objeto e atributo  
- [ ] d. objeto, atributo e classe  
- [x] e. objeto, classe e atributo

<br>

### 4. Dada a construção abaixo, associe os números ao elemento correspondente:

~~~TypeScript
let conta: Conta = new Conta();  
      1      2      3    4
~~~

( 4 ) Construtor  
( 3 ) Operador de instanciação  
( 2 ) Classe  
( 1 ) Objeto  

<br>

### 5. Crie uma classe chamada ControleDeAudio a partir das orientações:

**a. A classe deve ter um atributo inteiro representando o volume inicializado com o valor 2.**  
**b. Crie um método chamado aumentar volume que incrementa em um o valor atual. O método não deve deixar o valor ficar maior que 10. Utilize um if para isso;**  
**c. Crie um método chamado diminuir volume que decrementa em um o valor atual. O método não deve deixar o valor ficar menor 0.**  
**d. Crie um método chamado getVolume que retorna o valor do volume.**  

~~~TypeScript
class ControleDeAudio {
    private _volume: number = 2;

    aumentarVolume(): void {
        if (this._volume < 10) {
            this._volume += 1;                
        }
    }

    diminuirVolume (): void {
        if (this._volume > 0){
            this._volume -= 1;
        }
    }

    get volume (): number {
        return this._volume;
    }
}
~~~

<br>

### 6. Implemente a questão acima em outra linguagem que não seja TypeScript.  

Python (convertido pelo chat GPT)  

~~~Python
class ControleDeAudio:
    def __init__(self):
        self._volume = 2

    def aumentar_volume(self):
        if self._volume <= 9:
            self._volume += 1

    def diminuir_volume(self):
        if self._volume >= 1:
            self._volume -= 1

    @property
    def volume(self):
        return self._volume
~~~  

<br>

### 7. Na questão sobre retângulos do exercício anterior, crie um método que retorna verdadeiro ou falso se o retângulo é um quadrado. 

~~~typeScript
class Retangulo {
    l1: number = 0;
    l2: number = 0;

    calcularArea(): number {
        return this.l1 * this.l2;
    }
    
    calcularPerimetro(): number {
        return (this.l1 + this.l2)*2;
    }

    ehQuadrado(): boolean {
//      if (this.l1 === this.l2){
//          return true;
//      }
//      return false;

        return this.l1 === this.l2;  // melhor forma
    }
}
~~~  

<br>

### 8. Crie um método que chama o outro método calcularSaldo() e retorna uma string com os valores: Situação Positiva ou Situação Negativa com o valor entre parêntesis e em R$. 
 
~~~typeScript
class SituacaoFinanceira {
    valorCreditos: number = 0;
    valorDebitos: number = 0;

    calcularSaldo(): number {
        let saldo: number = this.valorCreditos - this.valorDebitos;
        return saldo;
    }

    situacao(): string {
        if ((this.calcularSaldo()) > 0){
            return `Situação Positiva (R$ ${this.calcularSaldo()})`;
        }else if ((this.calcularSaldo()) < 0){
            return `Situação Negativa (R$ ${this.calcularSaldo()})`;
        }else {
            return `Conta Zerada (R$ ${this.calcularSaldo()})`;
        }
    }
}

console.clear();

let sf: SituacaoFinanceira = new SituacaoFinanceira;
sf.valorCreditos = 100;
sf.valorDebitos = 100;
console.log(sf.situacao());

sf.valorCreditos = 100;
sf.valorDebitos = 90;
console.log(sf.situacao());

sf.valorCreditos = 70;
sf.valorDebitos = 100;
console.log(sf.situacao());
~~~
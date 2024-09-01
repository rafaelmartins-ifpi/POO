#### QUESTÃO 1
~~~typescript
function ehPar(numero: number): boolean {
    return numero % 2 === 0; 
} 
~~~
<br>


#### QUESTÃO 2
~~~typescript
function ehPrimo (numero: number): boolean {
    
    for (let i = 2; i < numero; i++){
        if (numero % i === 0) {
            return false;
        }
    }

    return true;
}
~~~
<br>


#### QUESTÃO 3
~~~typescript
function saudacao (nome: string, prenome?: string): void {

    if (prenome) {
        console.log (`Sr. ${nome} ${prenome}`);
    }else{
        console.log (`Sr. ${nome}`);
    }
}
~~~
<br>


#### QUESTÃO 4
~~~typescript
function arrayToString (array: number []): string {
    
    let mensagem: string = "";
    
    array.forEach((numero) => {
        mensagem += " - ";
        mensagem += numero.toString();
    })

    return mensagem.substring(3);
}
~~~
<br>


#### Questão 5
~~~typescript
function soma(x: number, y?: any): number {
    return x + y;
}

console.log(soma(1,2));    // 3
console.log(soma(1,"2"));  // 12
console.log(soma(1));      // Nan
~~~
<br>


#### Questão 6.
~~~typescript
function exibir(...letras: string[]): void {
    
    let elementos: string = "";
    
    for (let i=0; i < letras.length; i++){
        elementos += " ";
        elementos += letras[i];
    }

    console.log(elementos.substring(1));
}

exibir("a");
exibir("a", "b");
exibir("a", "b", "c");
exibir("a", "b", "c", "d");
~~~
<br>


#### QUESTÃO 7 
~~~typescript
const ola = () => {
    console.log("Olá !!");
}

ola();
~~~
<br>


#### QUESTÃO 8
~~~typescript
const array: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15];
const pares = array.filter(num => num % 2 === 0);

console.log (pares);
~~~
<br>


#### QUESTÃO 9 
~~~typescript
const elementos: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const dobroDosElementos: number[] = elementos.map(num => num * 2);
const somaDosAlementos: number = elementos.reduce((soma,num) => soma + num);

console.log (dobroDosElementos);
console.log (somaDosAlementos);
~~~
<br>


#### QUESTÃO 10


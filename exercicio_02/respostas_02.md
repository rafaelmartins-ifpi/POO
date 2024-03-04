## Respostas - Excercício 02  

### 1. Qual a diferença entre tipagem dinâmica e tipagem estática?  

A principal diferença entre tipagem dinâmica e tipagem estática está na forma como as variáveis e os tipos de dados são tratados em uma linguagem de programação.  

Na tipagem estática, os tipos de dados das variáveis são verificados em tempo de compilação. Assim, não permitem ao desenvolvedor alterar o tipo da variável depois de declarada.  

Na tipagem dinâmica, os tipos de dados das variáveis são verificados em tempo de execução. Refere-se à a habilidade da linguagem de programação em escolher o tipo de dado de acordo com o valor atribuído à variável em tempo de execução dinamicamente, sem gerar durante a compilação.  

<br>

### 2. Qual o principal problema do uso de tipagem dinâmica?  

Um dos principais problemas do uso de tipagem dinâmica é a maior possibilidade de erros de tipo ocorrerem em tempo de execução, podendo levar a falhas inesperadas durante o uso da aplicação, pois os tipos de tipos de dados não são verificados em tempo de compilação.  

Em resumo, pode-se elencar algumas preocupações (problemas) relacionadas ao uso de uma linguagem dinâmica: Erros em tempo de execução, falta de detecção de erros antecipadamente, código menos previsível, depuração complexa, desempenho reduzido, problemas de refatoração, etc.  

<br>

### 3. Pesquise um exemplo na internet em que a tipagem dinâmica pode ser problemático.  

A exemplo da linguagem Phyton, que é uma linguagem dinâmica de tipagem forte, se formos executar o código abaixo teremos o seguinte erro:  

~~~python
x = 5
print("O valor de x é:", x)

x = "Hello, World!"
print("Agora o valor de x é:", x)
~~~  

Neste exemplo, a variável x é inicialmente atribuída como um número inteiro e, em seguida, é reatribuída como uma string. Isso é permitido devido à tipagem dinâmica do Python. Embora essa flexibilidade possa ser conveniente em alguns casos, ela também pode levar a problemas difíceis de identificar e depurar, especialmente em programas grandes e complexos.  

Em uma linguagem com tipagem estática, isso seria detectado em tempo de compilação, mas em uma linguagem com tipagem dinâmica, esse código será executado sem erros de compilação.  

<br>

### 4. Pesquise  e  exemplifique  com  um  exemplo  porque  dizemos  que  a  linguagem  C, mesmo tendo tipagem estática, possui tipagem fraca.  

~~~c
#include <stdio.h>

int main() {
    int inteiro = 10;
    float pontoFlutuante = 5.5;

    float resultado = inteiro + pontoFlutuante;

    printf("O resultado é: %f\n", resultado);

    return 0;
}
~~~  

Neste exemplo, um inteiro (inteiro) é somado a uma variável de ponto flutuante (pontoFlutuante). Embora o tipo de inteiro seja int e o tipo de pontoFlutuante seja float, o resultado é automaticamente promovido para float durante a operação de adição. Isso ocorre porque a linguagem C permite a promoção automática de tipos em operações aritméticas, convertendo tipos "menos precisos" para tipos "mais precisos".

Essa flexibilidade pode ser útil em muitos casos, mas também pode levar a comportamentos inesperados se o programador não estiver ciente das regras de promoção de tipos. É um exemplo de tipagem fraca, pois permite que operações entre tipos diferentes sejam realizadas sem a necessidade de conversões explícitas, mas ainda mantendo a tipagem estática no sentido de que os tipos das variáveis devem ser declarados.  

<br>

### 5. Pesquise e, se encontrar, um exemplo onde o tipo any seria benéfico.  

O tipo "any" pode ser benéfico quando se lida com dados de tipos desconhecidos ou variáveis fontes externas, como entradas de usuário, API’s de terceiros ou arquivos de configuração, pois não se tem a certeza do tipo de entrada fornecido. Contudo, seu uso deve ser feito com cautela e somente quando necessário, pois pode introduzir possibilidades de erros em tempo de execução e comprometer a segurança do código.  

<br>

### 6. Poderíamos dizer que a tipagem do TypeScript é fraca por uma variável do tipo number aceitar tanto inteiros como ponto flutuante?  

Não, pois a tipagem forte ou fraca refere-se à restrição de operações entre tipos diferentes. Embora o tipo number aceite tanto inteiros como ponto flutuante, o TypeScript ainda é uma linguagem de tipagem forte porque não permite operações inválidas entre tipos diferentes sem as devidas conversões.  

<br>

7.  Reescreva o exemplo abaixo, mantendo a quebra de linhas usando template strings e os valores Ely, 120.56 e TypeScript venham de variáveis declaradas separadamente e “interpoladas” na string:  
Ely  
My payment time is 120.56  
and  
my preffered language is TypeScript  

~~~typescript
let nome: string = "Ely";
let tempo: number = 120.56;
let linguagem: string = "TypeScript";


function criarFrase (nome: string, tempo: number, linguagem: string) : string{
    let frase: string = `${nome} \n My payment time is ${tempo}\n and \n my preffered language is ${linguagem}`
    
    return frase;
}

console.log(criarFrase(nome, tempo, linguagem));
~~~  

<br>

### 8. Configure o seu arquivo de configuração do TypeScript com as seguintes opções:  
### a. Alterar o local em que os arquivos *.js são gerados para a pasta build;  
### b. allowUnreachableCode com valor true;  
### https://www.typescriptlang.org/pt/tsconfig#allowUnreachableCode 
### c. noImplicitAny com valor true  
### https://www.typescriptlang.org/pt/tsconfig#noImplicitAny  
### d. target com o valor ES3. Além disso, utilize a classe do exercício anterior e veja como ela é transpilada para JS;  
### e. strictNullChecks para true e crie um exemplo que mostre a restrição  


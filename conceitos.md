# Algoritmos e Programação II
## Teste de Software
O teste de software tem natureza inversa aos objetivos até aqui com o desenvolvimento de software. O teste de software tem natureza **destrutiva**. O objetivo do teste de software é encontrar falhas, seja de codificação, a partir de testes de funcionalidade, ou de outras naturezas, tais como: usabilidade, stress, desempenho, aceita

## Curiosidades
- O custo com a manutenção de software chega a ser **3 vezes mais caro do que o custo do desenvolvimento**;
- O Teste de Software custa entre 20% e 30% do investimento no desenvolvimento;
- Hoje, poucos profissionais são Testers "raiz". Existe muito profissional improvisado no teste.

### Testes funcionais
- Unidade; 
- Integração; 
- Sistema; 
- Aceitação;
- Alfa; 
- Beta;
- Regressão.

### Testes não-funcionais 
- Desempenho; 
- Carga;
- Compatibilidade; 
- Usabilidade; 
- Segurança;
- Robustez.

## Introdução a teste unitário
O teste unitário é responsável por testar as unidades do sistema. Ex.: métodos, retornos, entrada e saída de métodos

### Vantagens
Previne contra o surgimento de bugs oriundos de código mal escrito.
- Aumenta a confiabilidade do código testado;
- Reduz o medo de modificar o código;
- Testa situações de sucesso e de falha;
- É uma prática de diversas metodologias ágeis;
- **Serve como validação dos requisitos**.
### Desvantagens/Dificuldades
- Problemas culturais;
- Em projetos pequenos constuma ser dispensado.

### Quando testar
- Antes de escrever a regra de negócios;
- Antes de escrever qualquer linha de código da aplicação (TDD);
- Diariamente.

### Como testar
Poderíamos desenvolver classes "normais" que executam tentativas e apresentam mensagens específicas quando a aplicação falha. Porém, existem frameworks que foram desenvolvidos unicamente para fazer isso, que inclusive nos dão uma saída gráfica e de fácil interpretação e avaliação. Que é o caso do [JUnit](http://junit.org/junit4/javadoc/latest/) quando falamos em Java.

### Planejar, Executar e Testar
Para nos auxiliar a pensar nos testes, podemos seguir o seguinte guia: 
1. Defina uma **lista com os testes** a serem implementados
2. Implemente uma **classe de teste** e desenvolva um método de teste para uma das tarefas
3. Rode o **jUnit** e certifique-se que o teste irá falhar
4. Implemente o código mais simples que rode o teste
5. **Refatore** o código para remover a duplicação de dados
6. Caso necessário, escreva mais testes ou aprimore o existente
7. Faça esses passos até concluir toda a lista definida no item 1

### JUnit
O JUnit é um framework criado por Erich Gamma e Kent Beck, com suporte à criação de testes automatizados na linguagem de programação Java.
#### Classe Assert
Classe que possui uma série métodos estáticos (assertivas) que podem ser utilizados para realizaço dos testes

Exemplos de assertivas:
```java
// Irá validar o teste se o argumento for verdadeiro
assertTrue(boolean predicado)
// Irá validar o teste se um objeto for equal a outro
assertEquals(Object valorEsperado, Object valorTestado)
// Verifica se dois objetos são a mesma instância
assertSame(Object valorEsperado, Object valorTestado)
// Verifica se um objeto possui referência nula
assertNull(Object objetoTestado)
// Faz com que um teste falhe. Pode receber um valor por argumento
fail(...)
```

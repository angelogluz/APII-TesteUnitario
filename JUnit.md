# Teste Unitário com JUnit
## Estrutura básica
Uma classe de teste é uma classe composta por algumas anotações que indicam o que cada método representa.

Algumas das principais anotações são:

```java
@Test
```
Anotação aplicada a um método que irá indicar que o referido é um método de teste.

```java
@Before
```
Anotação aplicada a um método que irá indicar que o referido deverá executar antes de cada método de teste. Pode ser utilizada para garantir o estado inicial do caso de teste.

```java
@After
```
Anotação aplicada a um método que irá indicar que o referido deverá executar após cada método de teste. Pode ser utilizada para garantir que modificações ocorridas em um teste não afete outro teste.

```java
@BeforeClass
```
Anotação aplicada a um método que irá indicar que o referido deverá executar uma única vez, **antes** que os testes comecem. 

**O método com a anotaço BeforeClass deve ser estático, já que executa antes de tudo na classe**

```java
@AfterClass
```
Anotação aplicada a um método que irá indicar que o referido deverá executar uma única vez, **após** que os testes terminarem. 

**O método com a anotaço AfterClass, assim como o BeforeClass, também deve ser estático.**
### Código padrão de uma classe JUnit
```java
package local;

import org.junit.After;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Test;
import static org.junit.Assert.*;

/**
 *
 * @author angelogl
 */
public class ClienteTeste {
    
    public ClienteTeste() {
    }
    
    @BeforeClass
    public static void setUpClass() {
    }
    
    @AfterClass
    public static void tearDownClass() {
    }
    
    @Before
    public void setUp() {
    }
    
    @After
    public void tearDown() {
    }

    // TODO add test methods here.
    // The methods must be annotated with annotation @Test. For example:
    //
    // @Test
    // public void hello() {}
}
```
## Escrevendo Testes
Agora basta escrever os métodos de teste
**Dica importante!**
Organize seu código de teste dividido em 3 diferentes momentos: a definição do **cenário**, as **ações** que são as operações as quais se deseja avaliar a saída, e a **verificação**, que se trata do teste propriamente dito.

### Primeiro teste
Vamos escrever dois testes que irão verificar se o resultado da soma e da subtração entre dois valores está saindo conforme esperado. Ainda neste teste, vamos inserir um texto em cada um dos métodos anotados, afim de verificar os momentos em que eles estão sendo executados.

**Boa prática!**
É uma boa prática escrever um primeiro teste force uma falha.

#### Código
```java
package local;

import org.junit.After;
import org.junit.AfterClass;
import org.junit.Before;
import org.junit.BeforeClass;
import org.junit.Test;
import static org.junit.Assert.*;

/**
 *
 * @author angelogl
 */
public class ClienteTeste {
    
    public ClienteTeste() {

    }
    
    @BeforeClass
    public static void setUpClass() {
        System.out.println("BeforeClass");
    }
    
    @AfterClass
    public static void tearDownClass() {
        System.out.println("AfterClass");
    }
    
    @Before
    public void setUp() {
        System.out.println("Before");
    }
    
    @After
    public void tearDown() {
        System.out.println("After");
    }

    @Test
     public void deveSerPossivelRealizarOperacaoDeSoma() {
     //Cenario
     int valor1 = 10;
     int valor2 = 15;
     int resultado;
     
     //Ação
     resultado = valor1+valor2;
     
     //Validação
        assertEquals(90, resultado);
     
     }
         @Test
     public void deveSerPossivelRealizarOperacaoDeSubtracao() {
     //Cenario
     int valor1 = 30;
     int valor2 = 15;
     int resultado;
     
     //Ação
     resultado = valor1-valor2;
     
     //Validação
        assertEquals(1, resultado);
     
     }
}
```
#### A Saída
```java
BeforeClass
Before
After
Before
After
AfterClass
Tests run: 2, Failures: 2, Errors: 0, Skipped: 0, Time elapsed: 0.15 sec <<< FAILURE!

Results :

Failed tests:   deveSerPossivelRealizarOperacaoDeSoma(local.ClienteTeste): expected:<90> but was:<25>
  deveSerPossivelRealizarOperacaoDeSubtracao(local.ClienteTeste): expected:<1> but was:<15>

Tests run: 2, Failures: 2, Errors: 0, Skipped: 0
```
#### Correção
Após o teste falar, podemos corrigi-lo e reexecutar.
```java
@Test
     public void deveSerPossivelRealizarOperacaoDeSoma() {
     //Cenario
     int valor1 = 10;
     int valor2 = 15;
     int resultado;
     
     //Ação
     resultado = valor1+valor2;
     
     //Validação
        assertEquals(25, resultado);
     
     }
         @Test
     public void deveSerPossivelRealizarOperacaoDeSubtracao() {
     //Cenario
     int valor1 = 30;
     int valor2 = 15;
     int resultado;
     
     //Ação
     resultado = valor1-valor2;
     
     //Validação
        assertEquals(15, resultado);
     
     }
```
#### Resultado
```java
-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running local.ClienteTeste
BeforeClass
Before
After
Before
After
AfterClass
Tests run: 2, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.125 sec

Results :

Tests run: 2, Failures: 0, Errors: 0, Skipped: 0
```
## Prática
Desenvolva uma simples classe **Calculadora**, que realiza as 4 operações básicas. Em seguida, crie uma classe de teste com diversos métodos de teste para validar sua calculadora.

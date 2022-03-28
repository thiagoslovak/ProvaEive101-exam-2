1. Por que a execução do Java é realizada em pilha?

   - É usado a estrutura de dados Pilha para organizar a execução do código, lembrando o que ainda precisa ser executado. Assim a JVM organiza a execução e sabe exatamente qual método está sendo executado que é sempre o método no topo da pilha.

     

2. Em programação, qual(is) a(s) utilidade(s) de *debugar* um código?

   - Auxilia tanto de um melhor entendimento do código, como também para facilitar a resolução de erros em seu código.

     

3. Em Java, qual efeito as exceções possuem sobre o fluxo de execução da pilha? Por que, em muitos casos, o próprio desenvolvedor escreve códigos que intencionalmente lançam essas exceções?

   - Lançar uma exceção, indica que quer interromper a execução da pilha. Quando se escreve código que lança exceções, é para tratar um possível erro em seu código.

     

4. O que são e qual(is) a(s) diferença(s) entre as classes `Throwable`, `Exception` e `RuntimeException`?

   - Throwable -> É a Classe mãe para tratar as exceções, objetos que herdão de Throwable podem jogar exceções;

   - Exception -> Essa Classe é usada quando exceções devem ser tratados checked.

   - RuntimeException -> Essa Classe é usada quando a exceção pode ou não ser tratada unckecked.

     

5. O que são e qual(is) a(s) diferença(s) entre exceções _checked_ e _unchecked_?

   - checked -> Verificado pelo compilador, obriga os métodos deixar explicito na assinatura a tratativa de exceção ou fazer um try/catch para tratar.

   - unchecked -> As exceções não são verificadas pelo compilador, pode ou não ser tratadas.

     

6. Qual(is) a(s) diferença(s) entre uma exceção e um erro em Java?

   - Erro indica a situação em que a aplicação não deve tratar o erro. 

   - Exceção são possíveis erros que podem ser tratados.

     

7. Explique as *keywods* `try`, `catch`, `finally`, `throw` e `throws`.

   - try -> Sinaliza para JVM que o código é perigoso, a JVM tenta executar e se der algum exceção ...

   - catch -> Se der a exceção , pega essa exceção e trata de acordo com oque for necessário.

   - finally -> É um bloco que sempre será executado, muito usado quando se quer liberar recursos ocupados ao final da execução.

   - throw-> Usado para lançar uma exceção.

   - throws -> Indica que um trecho de código que chame esse método deve obrigatoriamente capturar uma possível exceção.

     

8. O que é e para que serve a interface `AutoCloseable`? Como funciona o *try with resources*?

   - AutoCloseable -> A implementação desta Interface permite que uma Classe seja utilizada como recurso da construção try-with-resources, que permite fechar os recursos automaticamente ao final de um bloco.

   - try-with-resources -> Garante que cada recurso seja fechado no final da instrução

     

9. Sobre pacotes, é correto afirmar que:

   1. É boa prática nomear os pacotes na estrutura `{site_ao_contrário}.{nome_do_projeto}`; :heavy_check_mark:

   2. Não devemos criar muitos pacotes, pois prejudica a navegação e legibilidade dentro do projeto; 

   3. O uso de pacotes corretamente está diretamente relacionado à qualidade arquitetural de um projeto, já que eles servem para organizá-lo; :heavy_check_mark:

      

10. Explique a(s) diferença(s) entre os modificadores de acesso `private`, `default` `protected` e `public` em Java.

    - private -> Acesso apenas dentro da Classe.

    - default -> Acesso apenas a Classes dentro do mesmo pacote.

    - protected -> Acesso na Classe e Classes filhas, Classes que não são herdadas não tem acesso.

    - public -> Acesso livre, pode ser acessado de qualquer lugar.

      

11. Qual a ordem correta dos itens abaixo, considerando a estrutura de um arquivo Java onde há somente uma importação e uma classe vazia? (considere * como _wildcard_)

    ```java
    // 1
    
    // 2
    
    // 3
    ```

    1. `package *;`, `imports *;` e `class * {}`;

    2. `package *;`, `import *;` e `class * {}`; :heavy_check_mark:

    3. `pack *;`, `imports *;` e `class * {}`;

    4. `pack *;`, `import *;` e `class * {}`;

       

12. Explique o que é FQN (Fully Qualified Name), sua estrutura e como evitamos ter de utilizá-lo sempre que referenciamos uma classe.

    - FQN -> Nome do pacote de onde é a Classe, para evitar de usar o FQN sempre que for usar uma Classe, é só fazer o import desse pacote. 

      

13. O que é, para que serve, como adquirir e como utilizar um arquivo JAR?

    - JAR -> É um conjunto de Classe, usualmente chamada de biblioteca. É usado quando se precisa se desenvolver algo especifico que as Classes padrão do Java não possuem. Por exemplo Jsoup biblioteca para se desenvolver Crawler.

      

14. O que é o pacote `java.lang` e por que ele é tão essencial para qualquer código Java?

    - É um pacote que é padrão do Java, já vem automaticamente importado. É essencial, por conta que esse pacote fornece Classes que são fundamentais para o uso da linguagem.

      

15. O que é uma `CharSequence` e qual(is) a(s) diferença(s) entre ela e uma `String`?

    - CharSequence -> É uma Interface que representa uma sequência de caracteres. Já a String é uma sequência de caracteres, porem é uma Classe.

      

16. Descreva os métodos da classe String citados abaixo:

    1. `.replace(char oldChar, char newChar);`

       - Usado para substituir um caractere de uma String.

    2. `.replaceAll(String regex, String replacement)`;

       - Usado para substituir uma String inteira.

    3. `.toLowerCase()`;

       - Usado para deixar um String com letras minúsculas. 

    4. `.concat(String str)`;

       - Usado para concatenar uma String a outra.

    5. `.contains(CharSequence s)`;

       - Usado para verificar se contem a CharSequence passada.

    6. `.equals(Object anObject)`;

       - Usado para verificar se Object passado é igual. 

    7. `.equalsIgnoreCase(String anotherString)`;

       - Usado para comparar uma String com outra String ignorando maiúsculas e minúsculas.

    8. `.isBlank()`;

       - Usado para determinar se uma determinada String está em branco ou vazia ou contém apenas espaços em branco.

    9. `.matches(String regex)`;

       - Usado para verificar se a String corresponde á expressão regular fornecida ou não.

         

17. Qual(is) a(s) diferença(s) entre `overriding` e `overloading` de métodos? Explique-os dando exemplos úteis da aplicação de ambos.

    - Overriding-> Usado para sobresser algum método.  

      ```java
      @Override
      public String toString() {
      	return "Numero: " + this.numero + ", Agencia: " + this.agencia;
      }
      //Sobrescrevendo o método toString.Naturalemte se não fosse sobrescrito, o método toString ia imprimir a referência do objeto.

    - Overloading -> Usado para sobrecarregar algum método.

      ```java
       public static int teste(int num){
        int teste;
        teste = num * num;
        return teste;
       }
      
        public static double teste(double num){
        double teste;
        teste = num * num;
        return teste;
       }
      
      //Exemplo alterando o tipo do retorno e o tipo dos parâmetros de entrada.
      ```

      

18. Todas as classes Java herdam a classe `Object`, que possui três métodos comumente sobrescritos: `.equals(Object obj)`, `.hashCode()` e `.toString()`. Explique a utilidade de cada um deles.

    - .equals(Object obj) -> Usado quando se tem a necessidade de verificar se o obj passado é igual.

    - .hashCode() -> Usado para retornar um valor de código hash para o objeto.

    - .toString() -> Usado para retornar uma representação da String do objeto. O toString retorna uma String que tem o nome da Classe, mais o '@' e um código hash do objeto.

      

19. Qual(is) das opções expressa(m) uma sintaxe correta para criar um *array* de inteiros?

    1. `int[] inteiros = []`;
    2. `int[] inteiros = new int[]`;
    3. `int[] inteiros = new int[]{999}`;:heavy_check_mark:
    4. `int[] inteiros = new int[1]`;:heavy_check_mark:
    5. `int[] inteiros = {999}`;
    6. `int... inteiros = {999}`;

20. Por que o primeiro código abaixo exibe o valor `0` no terminal, mas o segundo produz uma exceção?

    ```java
    // código 1
    class App {
        public static void main(String... args) {
            int[] inteiros = new int[1];
            System.out.println(inteiros[0]);
        }
    }
    
    //Exibe o valor 0 por conta que esta imprimindo um array e array trabalha com referência. Quando se da new em um alguns tipos de objetos, e imprime o valor. Naturalmente vem com 0.
    ```

    ```java
    // código 2
    class Pessoa {
        Endereco endereco;
    }
    
    class Endereco {
        String cep;
    }
    
    class App {
        public static void main(String... args) {
            Pessoa[] pessoas = new Pessoa[1];
            System.out.println(pessoas[0].endereco.cep);
        }
    }
    
    //Já aqui esta tentando acessar a referência que se tem dentro pessoas[0], e dentro deste index não tem nada. Não foi passado nada nesse index [0].
    ```

21. Sobre *type casting*, explique:

    1. *Cast* implícito; -> É quando se tem duas variáveis e a variável maior recebe a variável menor, mesmo que se for de tipos diferentes. Ai ocorre o Cast implícito, o compilador faz essa conversão sem a necessidade de deixar explícito a conversão. 

       

    2. *Cast* explícito; -> É quando se tem a necessidade de atribuir um valor da variável a outra, que uma delas é de um tipo maior. Ai se vem a necessidade de trucar esse valor, mesmo sabendo que pode perder algo, ai se faz o Cast explícito. Está deixando explícito que quer fazer essa conversão.

       

    3. `ClassCastException`; -> Exceção lançada para indicar que o código tentou converter um objeto em uma subclasse da qual não é uma instância. Quando alguém tenta converter um Integer para a String, String não é uma subclasse de Integer, então a `ClassCastException`será lançado.

       

22. Explique o que é e como utilizar o `autoboxing` e o `unboxing`.

    - autoboxing -> É quando JVM faz a conversão automática entre os tipos primitivos e suas Classes Wrapper. Exemplo, converter um int em um Integer. Internamente, o Java transforma o primitivo em um objeto.

      ````java
      int numero = 2;
      List<Integer> numeros = new ArrayList<Integer>();
      numeros.add(numero);
      //Adicionado um tipo primitivo em uma Lista de Inteiros.
      ````

      

    - unboxing -> É o contrario de autoboxing, a JVM faz a conversão de um Wrapper Integer para um tipo primitivo int.

      ````java
      int inteiro = 0;
      inteiro = new Integer(9);
      ````

      

23. É possível, no momento em que é executada uma aplicação em Java, passar argumentos para a mesma. Como isso pode ser feito e como podemos acessar esses argumentos dentro do código (no método `main()`)?

    - ````java
      Pelo terminal: Estando dentro bin/... Vá no terminal e escreva:
      java + pacote + nomeClasse + argumento
      
      Ou pela IDE IntelliJ, vá em Edit Configurations, selecione a Application, grid Build and run precha o campo Program arguments. Salva.
          
      public class Teste {
      
              public static void main(String[] args) {
                      for(int i = 0; i < args.length; i++) {
                          System.out.println(args[i]);
                      }
              }
      //Irá imprimir os argumentos passado.
      }
      ````

      

      

24. Ao utilizar um `array`, o tamanho máximo do mesmo deve ser declarado. Por que isso não acontece quando utilizamos `ArrayList`? E qual é o limite do que essa estrutura pode armazenar?

    - ArrayList -> Ao dar new em um ArrayList, automaticamente ele utiliza um array com um número pré-determinado de posições, que gira em torno de 1000.  Ele vai concatenando até chegar no limite da memória (OutOfMemoryError).

      

25. Por que, no geral, o `ArrayList` costuma ser mais utilizado que `arrays` em Java?

    - Uma das desvantagem de se usar array, o array possui tamanho fixo, não é possível remover uma posição do array. Já o ArrayList fornecer varias vantagem, podemos add elementos remover elementos, o tamanho do ArrayList  é dinamico. O ArrayList, é muito mais completo do que o Arrays.

      

26. Por que sempre devemos optar pelo uso de `Generics` ao declarar um `ArrayList` (declaração no formato `ArrayList<{tipo}>`)?

    - Para limitar essa ArrayList a armazenar apenas referencias do tipo informado.

      

27. Explique os métodos `.add(E e)` e `.contains(Object o)`, da interface `Collection`?

    - .add(E e) -> O método add()  insere o elemento especificado nesta coleção. Ele retorna um valor booleano 'true', se conseguir inserir o elemento na coleção especificada, senão retorna 'false'.

    - .contains(Object o) -> É usada para verificar se o elemento existe nesta coleção. Este método retorna um valor booleano que descreve a presença do elemento. Se o elemento estiver presente, ele retornará true, caso contrário, retornará false.

      

28. Explique as interfaces `Comparator<{tipo}>` e `Comparable<{tipo}>`.

    - Comparable<{tipo}> ->  Permite que uma determinada classe diga como uma instância dela deverá ser comparada com outras instâncias dela mesma. Para fazer essa comparação a Classe deve implementar a Interface Comparable e terá o método compareTo, implementando nesse método qual será a regra de comparação.

      

    - Comparator<{tipo}> -> Permite que você crie regras extras de comparação para as classes que você possui. Para fazer essa comparação a Classe deve implementar a Interface Comparator e terá o método compareTo, implementando nesse método qual será a regra de comparação.

      

29. Qual(is) a(s) diferença(s) entre as interfaces `List` e `Set`?

    - List -> É uma sequência ordenada de elementos. Ao usar o List, tem se o controle preciso sobre onde cada elemento se encontra na lista.

    - Set -> É uma lista distinta de elementos não ordenados. Um Set não pode conter elementos duplicados já uma List pode.

      

30. Como funciona a implementação `HashSet`? Qual a relação dela com o método `.hashCode()`?

    - HashSet -> Algumas caracteristicas, o HashSet não mantém a ordem dos elementos, oferece melhor desempenho, use o HashSet quando não quiser manter a ordem dos elementos da lista.

    - .hashCode() -> Esse método é usado para obter o valor hashCode para esta instância do HashSet. Ele retorna um valor inteiro que é o valor hashCode para esta instância do HashSet.

      

31. Por que é recomendado que o *overriding* dos métodos `.equals(Object obj)` e `.hashCode()` seja realizado sempre em pares (ao sobreescrever um, o outro também deve ser sobreescrito)?

    - Para manter o contrato geral do método .hashCode, que afirma que objetos iguais devem ter códigos de hash iguais.

      

32. Qual é a estrutura de uma expressão *lambda*, em Java? Explique e dê um exemplo, em código.

    ````java
    Expressão lambda simples, contém o parâmetro e uma expressão:
    parameter -> expression
        
    //Imports
       
    public class Teste {
    	public static void main(String[] args) {
            ArrayList<Integer> numero = new ArrayList<Integer>();
            numero.add(5);
        	numero.add(9);
        	numero.add(8);
        	numero.add(1);
            numero.forEach( (n) -> {System.out.println(n); } );
            //Para cada (n) que achar dentro de "numero", imprima na tela. 
        }
    }
    ````

    

33. Qual é a estrutura de uma expressão *lambda* utilizando *method reference*, em Java? Explique e dê um exemplo, em código.

    - ````java
      public class Teste {
      	public static void main(String[] args) {
              ArrayList<String> nomes = new ArrayList<String>();
              nomes.add("Thiago");
              nomes.add("Yara");
              nomes.add("Igor");
              nomes.add("Luan");
              nomes.forEach(System.out::println);
              //Dentro de System tem o método println, pega esse método e aplica sua função para cada elemento encontrado dentro de "nomes".
          }
      }
      ````

      

34. Qual é a estrutura de uma `stream`, em Java? Explique e dê um exemplo, em código.

    - ```java
       public static void main(String[] args) {
              ArrayList<Integer> lista = new ArrayList<Integer>();
              lista.add(1);
              lista.add(2);
              lista.add(1);
              lista.add(2);
              lista.stream()
                  	//Filtra, só pega os elementos que dividor por dois, resta 0.
                      .filter(e -> e % 2 == 0)
                  	//Faça uma busca(map), para cada elemento, multiple por 2.
                      .map(e -> e * 2)
                  	//Dentro de System tem o método println, pega esse método e aplica sua função para cada elemento encontrado dentro de "lista".
                      .forEach(System.out::println);     
      }
      
      //A ideia da stream() é iterar sobre essas coleções de objetos e, a cada elemento, realizar alguma ação, seja ela de filtragem, mapeamento, transformação, etc. 
      
      ```

      

35. O que falta no código abaixo para ser considerado um teste útil?

    ```java
    // package & imports
    class CalculadoraTest {
    
    	@Test
    	public void deveSomarDoisValores() {
            Calculadora calculadora = new Calculadora();
            int resultado = calculadora.somar(2, 2);
            //Do jeito que ta funciona.
            
            //Porém faltou, Assertions.assertEquals que compara se o valor esperado (4), é igual ao valor dentro de resultado. 
            Assertions.assertEquals(4, resultado);
    	}
    }
    ```

36. Como é aplicado o TDD? Qual(is) benefício(s) ele traz e quando devemos utilizá-lo?

    - No TDD primeiro começamos escrevendo o teste automatizado para depois implementar o código e por ultimo é a refatoração . É como se o teste fosse um rascunho, por meio do qual identificamos que Classe vamos criar, o seu nome, quais métodos usaremos, quais serão os parâmetros e o retorno desejado. A ideia é que, após escrever um teste e implementá-lo sem falhas, possamos revisar o código da implementação para deixá-lo mais funcional e organizado.

      

37. Quais métodos podemos utilizar para validar o lançamento de exceções em testes automatizados?

    - É usado o assertThrows(), dizendo que é esperando uma exceção.

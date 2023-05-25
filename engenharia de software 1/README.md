# bertoti

Software engineering repository

We see three critical differences between programming and software engineering: time, scale, and the trade-offs at play. On a software engineering project, engineers need to be more concerned with the passage of time and the eventual need for change. In a software engineering organization, we need to be more concerned about scale and efficiency, both for the software we produce as well as for the organization that is producing it. Finally, as software engineers, we are asked to make more complex decisions with higher-stakes outcomes, often based on imprecise estimates of time and growth.

Nós vemos três diferenças críticas entre programação e engenharia de software: tempo, escala e os trade-offs em jogo. Em um projeto de engenharia de software, os engenheiros precisam se preocupar mais com a passagem do tempo e a eventual necessidade de mudança. Em uma organização de engenharia de software, precisamos nos preocupar mais com escala e eficiência, tanto para o software que produzimos quanto para a organização que o produz. Por fim, como engenheiros de software, somos solicitados a tomar decisões mais complexas com resultados de alto risco, muitas vezes baseados em estimativas imprecisas de tempo e crescimento. 




-  As principais noções a longo prazo no ramo de engenharia de software, são diretamente voltadas a compensação. Todo investimento de tempo em prol da mudança nescessária aos engenheiros de software, é o que diferencia tal profissão dos programadores comuns. O segundo diferencial entre essas duas vertentes, visando precisão (já que as decisões que geralmente são de alto risco), seria a demanda  tempo de qualidade. 



Within Google, we sometimes say, “Software engineering is programming integrated over time.” Programming is certainly a significant part of software engineering: after all, programming is how you generate new software in the first place. If you accept this distinction, it also becomes clear that we might need to delineate between programming tasks (development) and software engineering tasks (development, modification, maintenance). The addition of time adds an important new dimension to programming. Cubes aren’t squares, distance isn’t velocity. Software engineering isn’t programming.

Dentro do Google, dizemos por vezes: "A engenharia de software é programação integrada ao longo do tempo". A programação é certamente uma parte significativa da engenharia de software: afinal de contas, a programação é a forma como se gera novo software em primeiro lugar. Se aceitar esta distinção, também se torna claro que podemos precisar de delimitar entre tarefas de programação (desenvolvimento) e tarefas de engenharia de software (desenvolvimento, modificação, manutenção). A adição de tempo acrescenta uma nova dimensão importante à programação. Os cubos não são quadrados, a distância não é velocidade. A engenharia de software não é programação.



-  é comum ouvirmos a frase: "A engenharia de software é a programação integrada ao longo do tempo". Isso significa que, embora a programação seja uma parte essencial da engenharia de software, ela não é a única. É necessário distinguir entre as tarefas de programação (como desenvolvimento de software) e as tarefas de engenharia de software (como modificação e manutenção do software). Além disso, o tempo é um elemento importante na engenharia de software, pois envolve a criação, modificação e manutenção de software ao longo do tempo. Portanto, a engenharia de software não pode ser reduzida apenas à programação. Assim como os cubos não são quadrados e a distância não é velocidade, a engenharia de software é muito mais do que apenas programação.


# O que são requisitos?
- Necessidades do cliente, o que o cliente precisa prioritariamente no projeto.
<h3>requisitos funcionais?</h3>

- É o que um sistema deve fazer, de modo verbal, serão as funcionalidades reais do sistema, por exemplo gerar um relatório, fazer um cálculo específico.
<h3>requisitos não funcionais?</h3>

- Como o sistema deve agir, quais os caminhos deve seguir para cumprir os requisitos funcionais, por exemplo em quais os dados serão inclusos e em qual formato o relatório será gerado. Qualidades do sistema.
<img src="https://user-images.githubusercontent.com/108089562/227500602-c1fdd604-51c4-497f-8c25-7e775757c7d2.png">

```java
  
  //classe 1
  public class App {
    public static void main(String[] args) throws Exception {
        Estoque estoque = new Estoque();
        
        // Criando alguns jogos de exemplo
        Game game1 = new Game();
        game1.setName("The Legend of Zelda: Breath of the Wild");
        game1.setConsole("Nintendo Switch");
        game1.setValor(59.99);
        
        Game game2 = new Game();
        game2.setName("Super Mario Odyssey");
        game2.setConsole("Nintendo Switch");
        game2.setValor(49.99);
        
        Game game3 = new Game();
        game3.setName("God of War");
        game3.setConsole("PlayStation 4");
        game3.setValor(39.99);
        
        // Cadastrando os jogos no estoque
        estoque.cadastrarGame(game1);
        estoque.cadastrarGame(game2);
        estoque.cadastrarGame(game3);
        
        // Testando a funcionalidade de buscar por nome
        List<Game> jogosPorNome = estoque.buscarPorNome("Super Mario Odyssey");
        System.out.println("Jogos encontrados por nome:");
        for (Game jogo : jogosPorNome) {
            System.out.println(jogo.getName() + " - " + jogo.getConsole() + " - R$" + jogo.getValor());
        }
        System.out.println();
        
        // Testando a funcionalidade de buscar por console
        List<Game> jogosPorConsole = estoque.buscarPorConsole("Nintendo Switch");
        System.out.println("Jogos encontrados por console:");
        for (Game jogo : jogosPorConsole) {
            System.out.println(jogo.getName() + " - " + jogo.getConsole() + " - R$" + jogo.getValor());
        }
        System.out.println();
        
        // Testando a funcionalidade de buscar por valor
        List<Game> jogosPorValor = estoque.buscarPorValor(39.99);
        System.out.println("Jogos encontrados por valor:");
        for (Game jogo : jogosPorValor) {
            System.out.println(jogo.getName() + " - " + jogo.getConsole() + " - R$" + jogo.getValor());
        }
        System.out.println();
    }
}

   
   //classe 2
import java.util.LinkedList;
import java.util.List;

public class Estoque {
    private List<Game> games = new ArrayList<>();
    
    public void cadastrarGame(Game game) {
        games.add(game);
    }
    
    public List<Game> buscarPorNome(String nome) {
        List<Game> resultados = new ArrayList<>();
        
        for (Game game : games) {
            if (game.getName().equalsIgnoreCase(nome)) {
                resultados.add(game);
            }
        }
        
        return resultados;
    }
    
    public List<Game> buscarPorConsole(String console) {
        List<Game> resultados = new ArrayList<>();
        
        for (Game game : games) {
            if (game.getConsole().equalsIgnoreCase(console)) {
                resultados.add(game);
            }
        }
        
        return resultados;
    }
    
    public List<Game> buscarPorValor(double valor) {
        List<Game> resultados = new ArrayList<>();
        
        for (Game game : games) {
            if (game.getValor() == valor) {
                resultados.add(game);
            }
        }
        
        return resultados;
    }
}



  //classe 3
public class Game {
    private String Name;
    private String Console;
    private double Valor;
    public String getName() {
        return Name;
    }
    public void setName(String name) {
        Name = name;
    }
    public String getConsole() {
        return Console;
    }
    public void setConsole(String console) {
        Console = console;
    }
    public double getValor() {
        return Valor;
    }
    public void setValor(double valor) {
        Valor = valor;
    }
}


  

```


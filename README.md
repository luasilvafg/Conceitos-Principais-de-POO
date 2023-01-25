# Conceitos-Principais-de-POO
POO? É o método (paradigma) de programação que usa tipos de dados personalizados. Em vez de operar apenas com tipos de dados primitivos, é possível construir novos tipos de dados.  Baseia-se fundamentalmente no conceito de Objetos. São mais fáceis de entender, corrigir e modificar. Os programas ficam modularizados em partes menores, o que torna mais fácil  manter o software. Dá pra reutilizar e reaproveitar pedaços de códigos já programados, mesmo em aplicações distintas.

CAPÍTULO 01 - Classe

É o conjunto de objetos que têm a mesma estrutura e o mesmo comportamento. Elas são “moldes” para criação de objetos. Servem para armazenar o conjunto de métodos que executam as tarefas dela. 
Uma das primeiras confusões que quem está começando a estudar orientação a objetos faz é confundir os conceitos de classes e objetos. Vamos ver mais um pouco desses conceitos para não deixarmos dúvidas.Classe representa o modelo do que queremos utilizar no nosso sistema; seria como um gabarito, um protótipo, a planta de uma casa ao realizarmos uma construção, a receita de um bolo.
Um bom exemplo seria quando temos as definições de uma classe que representa o carro do mundo real; ao lado, os objetos carros que iremos implementar no nosso sistema:
Assim, durante a execução do sistema, a cada carro que cadastramos uma cópia nova da classe carro é criada, e damos a ela características que irão diferenciá-la dos demais carros, ou seja, criamos a cada vez um novo objeto do tipo de carro.
Ah! Então quer dizer que classe é um tipo?  Isso mesmo. 
O principal benefício da utilização da programação por meio de classes é a reutilização do código, pois a cada objeto criado você não precisa criar sua estrutura novamente. 
Então escrevemos Atributos de objeto, que é o mais comum, pois o valor do conteúdo que será colocado é referente àquele objeto. Por exemplo, o Carro a no atributo Marca tem o conteúdo Ford, enquanto o Carro b tem o conteúdo Mitsubishi. Os atributos estão associados ao objeto; sua definição está feita na classe.
Porém, algumas vezes podemos querer um atributo que seja da classe, ou seja, é o mesmo para todos os objetos, podendo ser manipulados dentro da própria classe. Imagine um contador de carros numa loja, se cada objeto Carro tiver um atributo contador eu nunca conseguirei saber quantos carros eu tenho na minha loja. Nesse caso, em que criamos um atributo global, temos o que chamamos de atributo da classe, e em memória esse valor fica guardado no espaço reservado para a classe, e não para o objeto.

CAPÍTULO 02 - Objetos

Objeto é definido neste modelo como um conceito, abstração ou coisa com limites e significados bem definidos para a aplicação em questão. Objetos têm dois propósitos: promover o entendimento do mundo real e suportar uma base prática para uma implementação computacional. Não existe uma maneira “correta”de decompor um problema em objetos; esta decomposição depende do julgamento do projetista e da natureza do problema. Todos objetos têm identidade própria e são distinguíveis. Objetos classe suportam dois tipos de operações: referências a atributos e instanciação.    

Demonstração em código dos conceitos sobre Classes e objetos:

class Caneca: # esse 'molde' é usado pra criação dos objetos.
    formato = 'cilíndrica com alça' #atributo estático, não muda de valor
    def __init__(self, cor, logo): #inicializando as características da classe
        self.cor = cor #referenciando uma característica do próprio objeto
        self.logo = logo #referenciando uma característica do próprio objeto
        self.status = 'cheia' #referencia uma característica já pré-definida


    def beber(self): #criando método que serve pra atribuir um comportamento
        self.status = 'está vazia' #vou chamar essa string pra esse método
        return f'Estou bebendo da {self.logo}'


    def encher(self): #criando método
        self.status = 'está cheia'
        return f'Estou enchendo a {self.logo}'

class CanecaIFPI(Caneca):
    def __init__(self):
        super().__init__('verde', 'IFPI')
   
    def extras(self):
        print('Como bônus vc ganhou uma colher')

class CanecaBatman(Caneca):
    def __init__(self):
        super().__init__('preta', 'Batman')


    def extra(self):
        print('Eu sou batman')
       
caneca_ifpi = CanecaIFPI()
caneca_batman = CanecaBatman()
caneca_ifpi.extras()
caneca_batman.extra()

print(caneca_batman.beber())

CAPÍTULO 03 - Encapsulamento

Na programação orientada a objetos, o encapsulamento é feito em uma classe. A classe define a estrutura (dados) e o comportamento (código) que serão compartilhados entre os diversos objetos do sistema. Os objetos, por sua vez, contém a estrutura e comportamento da classe, como se fossem moldados por ela. Nesse contexto, encapsular os dados de uma aplicação significa evitar que estes sofram acessos indevidos. Para isso, é criada uma estrutura que contém métodos que podem ser utilizados por qualquer outra classe, sem causar inconsistências no desenvolvimento de um código. Por exemplo, atributo como data de nascimento e operação como o cálculo da idade. 
Em outras palavras, encapsular significa esconder a estrutura de dados, consistindo na parte privada (private), protegida (protected) e na parte pública (public). 

CAPÍTULO 04 - Herança

Herança é o processo no qual um objeto obtém propriedades de um outro objeto, em que o conhecimento normalmente é gerenciável através de classificações hierárquicas. Sem o uso de hierarquia, cada objeto precisaria definir todas as suas características explicitamente. Porém, usando herança, um objeto precisa definir apenas o que o torna único para a sua classe. 
Por exemplo, a classe Animal pode ser definida pelos seus atributos e comportamentos. (Atributos: tamanho, inteligência; Comportamentos: comer, respirar, dormir). A classe Mamífero é uma versão mais específica de Animal, mas que herda todos os atributos e comportamentos da classe mais geral (Atributos específicos: tipos de dentição, glândulas mamárias; Comportamentos: amamentar).
A herança interage diretamente com o encapsulamento. Se uma superclasse encapsula alguns atributos, então uma subclasse irá herdar esses atributos além daqueles definidos especificamente por ela. 

CAPÍTULO 07 - Interface

Podemos definir como interface o contrato entre a classe e o mundo exterior. Quando uma classe implementa uma interface, se compromete a fornecer o comportamento publicado por esta interface. As classes ajudam a definir um objeto e seu comportamento e as interfaces que auxiliam na definição dessas classes. As interfaces são formadas pela declaração de um ou mais métodos, os quais obrigatoriamente não possuem corpo. As operações específicas para cada um desses métodos são realizadas pela classe que implementa. De um modo geral, pode-se dizer que as interfaces definem certas funcionalidades, as quais dependem das classes que implementam as interfaces para que os métodos existam.

CAPÍTULO 06 - Polimorfismo

O polimorfismo permite que o interior de um método seja alterado para ser usado por outros objetos. Assim, há a reutilização do código, mas se cria um adendo virtualizado para a modificação necessária. 
Um mesmo chamado para um método pode invocar vários métodos diferentes. É uma consequência natural da herança. Permite que mensagens iguais sejam enviadas a objetos que responderão diferentemente. 
Por exemplo, uma chamada da operação “Calcular Saldo” de correntista, invoca as derivações correspondentes para cálculo de saldo de poupança, renda fixa, etc. 
 
CAPÍTULO 07 - S.O.L.I.D: Os 5 princípios da POO
S — Single Responsibility Principle (Princípio da responsabilidade única)
O — Open-Closed Principle (Princípio Aberto-Fechado)
L — Liskov Substitution Principle (Princípio da substituição de Liskov)
I — Interface Segregation Principle (Princípio da Segregação da Interface)
D — Dependency Inversion Principle (Princípio da inversão da dependência)


1. SRP — Single Responsibility Principle:

Princípio da Responsabilidade Única — Uma classe deve ter um, e somente um, motivo para mudar. Quando se atribui a uma classe mais de uma responsabilidade está se criando classes que fazem de tudo — God Class.
Vantagens: Código mais limpo e de fácil manutenção.
É mais fácil fazer alterações, por causa dos testes unitários. 
As responsabilidades das classes precisam ser divididas.
Esse princípio não se limita às classes. 

2. OCP — Open-Closed Principle:

Princípio Aberto-Fechado — Objetos ou entidades devem estar abertos para extensão, mas fechados para modificação, ou seja, quando novos comportamentos e recursos precisam ser adicionados no software, devemos estender e não alterar o código fonte original.
Vantagem: Facilidade na adição de novos requisitos, diminuindo as chances de introduzir novos bugs.
A interface é um dos exemplos mais utilizados no SOLID, pois ao usá-la precisou ter um nível de abstração maior para analisar o domínio.

3. LSP— Liskov Substitution Principle:

Princípio da substituição de Liskov — Uma classe derivada deve ser substituível por sua classe base. (‘Subtypes must be substitutable for their base types.’)
Vantagens: Permite usar o polimorfismo com mais confiança. Pode-se chamar as classes derivadas referindo-se à sua classe base sem preocupações com resultados inesperados.

4. ISP — Interface Segregation Principle:

Princípio da Segregação da Interface — Uma classe não deve ser forçada a implementar interfaces e métodos que não irão utilizar.
Esse princípio basicamente diz que é melhor criar interfaces mais específicas ao invés de termos uma única interface genérica.

5. DIP — Dependency Inversion Principle:

Princípio da Inversão de Dependência — Depende de abstrações e não de implementações. 
Quanto mais uma classe utilizar só uma classe, vai ser melhor pra manutenção, pra poder chamá-la pra um lugar específico.
Ver como funciona uma Injeção de Independência 

CAPÍTULO 08 - DESIGN PATTERNS 

Padrões de projeto são modelos já implementados e testados em diversos projetos e, por isso, sua utilização apresenta diversas vantagens, como maior segurança no uso e ganho no desenvolvimento. Os primeiros padrões utilizados foram GoF (Gang of Four), apresentados no livro Padrões de Projeto: soluções reutilizáveis de software orientado a objetos. Cada padrão de projeto é dividido em seções, estruturas que englobam e introduzem o padrão de projeto, possibilitando comparações, entendimento e aplicabilidade. Elas auxiliam e justificam o uso do padrão escolhido. São elas:
Nome e Classificação do Projeto: Expressa a essência do projeto;
Intenção e Objetivo: Busca entender o que o padrão faz, quais os seus princípios, além de tratar sobre o problema;
Outro nome representado: Outros nomes para reconhecer o padrão, caso existam;
Motivação: Cenário que ilustra um problema e como o padrão de projeto pode solucioná-lo;
Aplicabilidade: Onde o padrão pode ser aplicado e quais problemas pode resolver;
Estrutura: Representação gráfica das classes do padrão usando uma notação baseada em UML;
Participação e Colaboração: Classes ou objetos que participam do padrão de projeto e suas responsabilidades;
Consequências: analisar quais os custos e benefícios;
Implementação: Sugestões técnicas para conhecer o padrão;
Exemplo de Código e Usos Conhecidos: Blocos de códigos que ilustram o padrão de projeto e exemplos do padrão em sistemas reais;
Padrões Relacionados: apontar os padrões que complementam o padrão escolhido.

Padrões de Criação

Fornecem um guia de como instanciar objetos. Esta ação normalmente envolve decisões dinâmicas para escolher, por exemplo, qual classe instanciar ou a quais objetos delegar responsabilidade. É possível criar um objeto sem se preocupar com o todo envolvido na criação desse componente. Esse padrão nos mostra como estruturar e encapsular essas decisões. Há cinco padrões de criação GoF: Abstract Factory, Builder, Factory Method, Prototype e Singleton. 
Abstract Factory: fornece uma interface para a criação de conjuntos de objetos relacionados ou dependente , sem precisar especificar sua classe Builder: separa a construção de um objeto complexo da sua representação. Possibilita que seu processo de construção crie diferentes representações.
Builder: utiliza uma interface única compartilhada com todos os objetos que constroem outros objetos. Esta interface tem a responsabilidade de definir esse processo de construção. Ele é usado para encapsular a lógica de construção de um objeto.
Factory Method: define a interface para a criação de um objeto, mas são as subclasses que decidem qual classe deve ser instanciada.
Prototype: especifica os tipos de objetos a serem criados usando uma
instância prototípica e criando objetos copiando esse protótipo.
Singleton: garante que a classe tenha somente  uma instância e fornece
um ponto global de acesso a ela.

Demonstração em código do padrão Factory

from abc import ABCMeta, abstractmethod
class Music():
   __metaclass__ = ABCMeta
   @abstractmethod
   def do_play(self):
       pass
class Mp3(Music):
   def do_play(self):
       print ("Playing .mp3 music!")
 
class Ogg(Music):
   def do_play(self):
       print ("Playing .ogg music!")
 
class MusicFactory(object):
   def play_sound(self, object_type):
       return eval(object_type)().do_play()
 
if __name__ == "__main__":
   mf = MusicFactory()
   music = input("Which music you want to play Mp3 or Ogg")
   mf.play_sound(music)


Padrões Estruturais 

Tratam da composição de classes e objetos para formar estruturas complexas. São associados à maneira como classes e objetos são organizados estruturalmente e oferecem formas efetivas para usar conceitos OO como herança e composição. O objetivo desse padrão é a organização e a estruturação das  classes e dos seus relacionamentos com os objetos. Ao contrário do padrão de criação, o padrão de estrutura é voltado para os objetos , descrevendo maneiras de mantê-los, isto é, a maneira como as classes e os objetos serão compostos para formar estruturas maiores.
Há sete padrões estruturais GoF: Adapter, Bridge, Composite, Decorator, Façade, Flyweight e Proxy.
Adapter: converte a interface de um a classe em outra interface esperada pelo cliente. O Adapter permite que as classes trabalhem em conjunto para promover essa mudança.
Bridge: se para uma abstração da sua implementação o, permitindo uma variação individual de cada  uma.
Composite: compõe objetos em estruturas hierárquicas, como árvores. Trata objetos individuais e composições de objetos de forma uniforme.
Decorator: atribui de forma dinâmica responsabilidades adicionais a um objeto.
Façade: fornece uma interface unificada para um conjunto de interfaces em subsistema.
Flyweight: suporta grandes quantidades de objetos de forma eficiente, por meio de compartilhamento.
Proxy: fornece um objeto representante (surrogate) ou marcador de outro objeto.


Demonstração em código do Padrão Façade

Problema sem usar o método de fachada: Em um cenário hipotético, existe uma máquina de lavar que pode lavar, enxaguar e girar a roupa, mas todas as tarefas são realizadas separadamente. Como todo o sistema é bastante complexo, é preciso abstrair as complexidades dos subsistemas. Precisa-se de um sistema que possa automatizar toda a tarefa sem nenhuma interferência.
Solução usando o método de fachada: Para resolver o problema, pode-se contratar o Método da Fachada. Ele ajuda a ocultar ou abstrair as complexidades dos subsistemas como segue o código abaixo:
  
class Washing: 
    def wash(self): 
        print("Washing...") 
  
class Rinsing: 
    def rinse(self): 
        print("Rinsing...")   
class Spinning: 
    def spin(self): 
        print("Spinning...") 
  
class WashingMachine:  
    def __init__(self): 
        self.washing = Washing() 
        self.rinsing = Rinsing() 
        self.spinning = Spinning() 
  
    def startWashing(self): 
        self.washing.wash() 
        self.rinsing.rinse() 
        self.spinning.spin() 

if __name__ == "__main__": 
    washingMachine = WashingMachine() 
    washingMachine.startWashing()
    

Padrões Comportamentais

O objetivo é delegar responsabilidades, deﬁnindo como os objetos devem se comportar e se comunicar. Esses padrões se concentram nos algoritmos. Têm a ver com a maneira pela qual responsabilidades são distribuídas a classes e objetos durante a realização  de uma tarefa . São abstrações de aspectos comportamentais. São 11 os padrões comportamentais , que são descritos a seguir.
Chain of Responsibility: evita acoplamento de remetente de uma solicitação a o destinatário, dando chance a o objeto para tratar a solicitação.
Command: encapsula uma solicitação como objeto, permitindo parametrizar clientes com diferentes solicitações , enfileirando ou registrando os “logs” de solicitações.
Interpreter: define para a linguagem uma representação gramatical dentro do interpretador. 
Iterator: possibilita o acesso sequencial dos elementos de um a agregação de objetos, sem a necessidade de expor sua representação subjacente.
Mediator: define um objeto que encapsula a forma como um conjunto de objetos interage.
Memento: captura e externaliza um estado interno do objeto sem violar seu encapsulamento, possibilitando restaurar para esse estado — por exemplo, um controle de históricos de ações.
Observer: define uma dependência um-para-muitos entre objetos; quando um objeto muda, todos os seus dependentes são notificados e atualizados automaticamente.
State: permite que o objeto altere seu comportamento quando o estado interno for modificado.
Strategy: define uma família de algoritmos , encapsulando cada um e os tornando intercambiáveis.
Template Method: define o esqueleto de um algoritmo em uma operação, postergando a definição de alguns passos para subclasses.
Visitor: representa uma operação a ser executada sobre os elementos da estrutura de um objeto.

Demonstração em código do Padrão Strategy

from types import MethodType
class Animal(object):
 
   def __init__(self, *args, **kwargs):
       self.name = kwargs.pop('name', None) or 'Animal'
       if kwargs.get('walk', None):
           self.walk = MethodType(kwargs.pop('walk'), self)
   def walk(self):
       """
       Faz com que a instância animal (Animal) ande;
     A funcionalidade caminhar (walk) é uma estratégia e sua intenção é ser implementada separadamente para diferentes tipos de animais.
       
       """
       message = '{} should implement a walk method'.format(
           self.__class__.__name__)
       raise NotImplementedError(message)
# Aqui são alguns algoritmos diferentes de andar que podem ser usados com o animal (Animal)
def snake_walk(self):
   print('I am slithering side to side because I am a {}.'.format(self.name))
def four_legged_animal_walk(self):
   print('I am using all four of my legs to walk because I am a(n) {}.'.format(
       self.name))
def two_legged_animal_walk(self):
   print('I am standing up on my two legs to walk because I am a {}.'.format(
       self.name))







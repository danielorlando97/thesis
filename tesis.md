# Preguntas

- En la actualidad se escribe la menor cantidad de código para lograr
  un producto adecuado para un dominio determinado?????

  Motivación: Dado el estudio y desarrollo de backends, diseñados bajo las
  ideas de arquitecturas como DDD y Clean, se obtiene una gran cantidad de
  código que le aportan al resultado final las caracteristicas de ser robusto,
  escalable y sostenible en el tiempo. Pero tambien parece ser código fácilmente
  generable, pues consta de varios tipos que comparten la misma estructura y
  propiedades (DomainEntity, PersistenEntity, Dtos), 2, 3 y 4 clases para la
  resolución de un mismo problema (Controller, Service o UseCase, Repository y Domain)

  Referencia o Ejemplo: Los Orm; con estas herramientas podemos definir e interactuar
  con las base de datos sin necesidad de escribir código en SQL. Aunque estos existan
  siempre queda algun caso donde es necesario usar SQL, pero los orm disminuye esos
  casos, disminuyen la cantidad de código y optimizan la productividad

- Es posible definir un lenguaje formal que exprese los tipos, reglas y
  procesos válidos en un dominio determinado??????

  primera propuesta: code-example/domain-lang/warehouse.example.3d

- Es posible generar a partir de dicho lenguaje toda la infraestructura necesaria
  para logra un software robusto, escalable y mantenible?????

  Primera Impresión: A priori se conoce que aunque toda la estructura parece generable
  por su forma monotona, se reconoce que la funcionalidad de un software no solo esta
  determinado por su dominio, pues siempre es necesario definir cuestiones importantes
  en la infraestructura.

  Posibles Soluciones:

  - Lograr que el compilador pueda generar todas las posibles necesidades
  - Definir un lenguaje intermedio y ofrecer las herramientas para que todo usuario
    del lenguaje pueda definir como quiere generar su infraestructura
  - Correr el riesgo de perder en expresividad y abrir al lenguaje a que conozca sobre
    su infraestructura

- Como la infraestructura tambien determina las características del producto final, quizás
  el enfoque no es el adecuado. Es posible dada una infraestructura concreta generar la
  gramática de un DSL o un entorno de ejecución, para asi poder desarrollar en un lenguaje
  mas simple y en que lleve menos tiempo lograr un producto de calidad ???????

  Primera Impresión: A primera vista, parece ser un enfoque mas alcanzable, pero se preven
  posibles contras:

  - Si la infraestructura define tu lenguaje esto potencialmente podría llegar a
    suponer un DSL por infraestructura
  - Si la infraestructura define tu lenguaje entonces potencialmente ya no estamos hablando
    de un lenguaje que exprese puramente el dominio, sino posible comprimido de todas las
    capas de la arquitectura (que tambien es una solución a la pregunta inicial)

- Es el desarrollo de backends, la unica rama a la que se le puede aplicar el resultado de
  las respuestas anteriores?????

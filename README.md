# template-hexagonal-python


## Arquitetura Hexagonal com DDD: Template Python

Este template provê uma estrutura básica para a construção de aplicações Python seguindo a arquitetura hexagonal e os princípios do Domain-Driven Design (DDD).

### O que é Arquitetura Hexagonal?

A arquitetura hexagonal, também conhecida como arquitetura de portas e adaptadores, visa isolar o núcleo da aplicação (Domínio) de detalhes de implementação específicos, como frameworks, bancos de dados e interfaces de usuário. Isso permite que o domínio evolua independentemente das preocupações externas, tornando a aplicação mais flexível e fácil de manter.

### DDD e o Domínio

O Domain-Driven Design (DDD) é uma abordagem para desenvolvimento de software que se concentra no domínio do problema e na construção de um modelo rico que o represente. No contexto da arquitetura hexagonal, o domínio se torna o núcleo da aplicação, contendo a lógica de negócio principal.

### Estrutura do Template

O template organiza o código em pastas que refletem os diferentes componentes da arquitetura hexagonal:

**1. `src`**: Contém o código fonte principal da aplicação.

* **`project-name`**: Nome do seu projeto (substitua pelo nome real).
* **`adapters`**: Responsável por conectar o domínio com o mundo exterior.
  * **`inbound`**: Adaptadores que recebem requisições de fora da aplicação (e.g., API REST, CLI).
  * **`outbound`**: Adaptadores que interagem com sistemas externos (e.g., banco de dados, serviços externos).
* **`domain`**: Coração da aplicação, contendo a lógica de negócio e as entidades do domínio.
  * **`entities`**: Objetos que representam os conceitos chave do domínio (e.g., Cliente, Pedido).
  * **`exceptions`**: Exceções específicas do domínio.
  * **`factories`**: Responsável por criar instâncias de entidades e objetos de valor.
  * **`ports`**: Interfaces que definem como o domínio interage com o mundo exterior.
  * **`services`**: Orquestram as entidades e objetos de valor para implementar a lógica de negócio complexa.
  * **`use_cases`**: Representam ações específicas do usuário, encapsulando a lógica necessária para executá-las.
  * **`value_objects`**: Objetos imutáveis que descrevem características de entidades (e.g., CPF, Endereço).
  * **`__init__.py`**: Arquivo que define o pacote Python.

**2. `.gitignore`**: Lista de arquivos e pastas que devem ser ignorados pelo Git.

**3. `README.md`**: Este arquivo, contendo a documentação da aplicação.

### Benefícios da Arquitetura Hexagonal com DDD

* **Maior testabilidade**: O isolamento do domínio facilita a criação de testes unitários focados na lógica de negócio.
* **Flexibilidade e Adaptabilidade**: Facilita a troca de tecnologias (e.g., banco de dados, framework web) sem afetar o domínio.
* **Manutenibilidade Aprimorada**: Mudanças em partes específicas da aplicação são mais fáceis de implementar, sem impacto em outras áreas.
* **Domínio Rico e Expressivo**: DDD incentiva um modelo de domínio preciso e compreensível, melhorando a comunicação entre desenvolvedores e especialistas de domínio.

### Considerações

Este template serve como ponto de partida para projetos Python que utilizam a arquitetura hexagonal e DDD. Adapte-o às suas necessidades específicas, adicionando novas pastas, arquivos e dependências conforme necessário.
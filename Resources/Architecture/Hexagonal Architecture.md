# Hexagonal Architecture

- Quem guia a aplicação? Ator primário!! (API, Fila, CLI, Testes, Browser (GUI), etc)
- Ator primário: condutor (esquerda)
- Ator secundário: conduzido (direta)
- Porta:
  - é uma interface da OOP
  - Porta primária:
    - são casos de uso
    - expõe APIs de comunicação
    - chamadas executadas pelos atores primários
  - Porta secundária
    - expõe service provider interface (SPI)
    - chamadas executadas pelo hexágono
- Repository: Ator secundário que devolve resposta ao hexágono
- Recipient: Ator secundário que NÃO devolve resposta ao hexágono
- As classes que vão implementar os casos de uso (portas primárias) devem obrigatoriamente estar dentro do hexágono
- As classes de dentro do hexágono devem ser agnósticas a tecnologias / infraestrutura
- Centro do hexágono (Core) não pode depender das portas
- As classes que vão implementar as portas secundárias devem obrigatoriamente estar fora do hexágono
- As classes de fora do hexágono usam tecnologias específicas e traduzem (Adapter) as chamadas de negócio agnósticas a uma solução externa
- Adaptadores:
  - permitem que tecnologias externas interajam com as portas do hexágono
  - deve haver um adaptador específico para cada tecnologia que for utilizada
  - Driver Adapter (condutor):
    - são classes que usam frameworks e tecnologias específicas
    - converte uma solicitação de tecnologias específicas para solicitação agnósitca do hexágono
    - converte o input (lado esquerdo) para dentro do centro do hexágono (Core)
    - para cada porta condutora, deve haver pelo meno 2 adaptadores: 1- testar o comportamento; 2- usar a tecnologia requerida pela solução;
    - exemplos: suite de testes automatizados, app desktop, app mobile, web app, filas de mensageria
  - Driven Adapter (dirigido):
# Reactive programming

- Não é um paradigma de programação
- Reactive programming != Reactive systems
- Event loop (I/O reactor, Netty, AsyncHttp)
- RxJava, Reactor, Mutiny

## Características

- Publisher
  - Multi (0 .. N ou erro) Flux, Mono
  - Single (0 .. 1 ou erro) Observable, Single
- Lazy evaluation
  - nada acontece se alguém nao se inscrever
- Hot vs Cold publishers
  - Hot = continua acontecendo sem voltar (stream)
  - Cold = escolhe onde e pode voltar
- Schedulers
  - Ao invés de low level threading
- Observer pattern
- Pull vs Push (+ backpressure (buffer or drop for subscribe handle the demand))
- iterable-iterator vs publisher-subscriber
- Programação funcional e callbacks
- Bom para I/O bound

## Beneficios

- Abstrai complexidade (threading, concorrencia, locks, latches, etc)
- menos boilerplate
- Melhor latência e throughput - se comparado com padrão thread-per-request

## Async vs Reactive vs Default

- Default:
  - Request response model, thread faz a requisição e fica aguardando o retorno (thread parada)
  - Codigo sincrono simples de entender
- Async
  - Usando Async com 2 CompletableFuture, por exemplo, a thread main fica aguardando as duas promessas terminarem
  - Duas requisições são feitas de forma concorrentes simultaneamente. Gasta mais threads
- Reactive
  - Reativa não bloqueante (Non-Blocking I/O)
  - No codigo, mandamos um callback
  - Ganhamos tempo, como async e gastamos menos threads (delegado para o event loop? Netty e kernel)
  - Mono, por exemplo, n ocupa thread


# Referencias

- https://www.youtube.com/watch?v=7DgcCNn9mA8
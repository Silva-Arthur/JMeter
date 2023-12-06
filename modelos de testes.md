# Modelos de testes

* Teste de carga - Load Test

    A aplicação é submetida a uma carga, a carga esperada em prod, e é avaliado o comportamento.

* Teste de estresse - Stress Test

    Submeter o sistema a condições hostis, um volume maior que o esperado, para encontrar até onde irá o limite do funcionamento, começando com um número menor e aumentando conforme os testes irão se seguindo. Ajuda a verificar se o sistema está escalando na nuvem.

* Teste de pico - Peak Test

    Teste de pico, testado em prod, para verificar, por exemplo, o consumo na black friday, para poder verificar como a aplicação se comporta no momento do pico de uso.

* Teste de continuidade - Soak Test

    Visa usar uma carga próxima de prod, por um longo período, semanas talvez, busca verificar falhas como memory leak relacionada com o garbage collector, memória, uso de banda etc. Geralmente executado em produção.

<br>

# Terminologias

* Baseline 

    Criação de uma linha de base, onde é executado vários testes, a linha de base serve como métrica inicial, para ter uma base comparativa para o futuro.

* Benchmarking

    Comparar os resultados com o valor obtido pelo **BASELINE**, ou com algum indicador e métrica padrão da indústria.

* Métricas

    Resultados que podem ser compreendidos em uma escala.

* Saturação

    Ponto onde o sistema e o recurso atingiu a utilização total, pode-se ver, quando o resultado começa a apresentar uma degração, pode-ser perceber que o sistema saturou.

* Workload
    
    Carga de trabalho, número de usuários, usuários simultâneos, volumes de dados, volumes de transações.

* Think Time

    Intervalo de tempo entre duas requisições no sistema.

* Ramp Up

    Aumento gradual de carga em um teste.

* Steady State

    Melhor período para analise dos resultados, depois do **RAMP UP**, pois o sistema já chegou no pico de uso programado e não vai mais sofrer estresse que aumente o processamento.

<br>

# Defeitos em testes de performance

* Timeouts

    Tempo de resposta fica lento, geralmente configurado no servidor.

* Tempo de Resposta
    
    Tempo que o sistema demora para processar e dar o retorno, conforme o aumento da carga, o tempo de resposta vai diminuindo.

* Falha de Caching

    Pode apontar se o mecanismo de cache está ou não está funcionando.

* Memory Leak

    Identificar se alguma rotina não está tratando o lixo de memória de forma adequada, veremos um aumento de memória, normalmente aparece num teste de carga ou stress.

* Corrupção de Dados

    Uma quantidade excessiva de requests pode gerar problemas, como a corrupção de dados, susbstituição de arquivos que, por exemplo, usem timestamp. Pode estar relacionada com problemas de gravação no banco de dados e leitura.

* Load Balancer

    Verficar se o **load balancer** está distribuindo bem, se está balanceando bem as requisições entre as maquinas, para não deixar ninguém sobrecarregado.

* Exposição de Dados

    Pode gerar erros da categoria 500, expondo dados do servidor, stack trace, cache, informações do banco de dados e outros.

* Latência

    Atraso  que uma solicitação leva de um ponto a outro, deveria tender a 0, quanto menor melhor. Medida em milissegundos. Problema que pode não ser só do sistema mas também da infraestrutura da rede.

* Largura de Banda

    Capacidade de bits que podem ser trafegados em um determinado canal, volume relacionado no teste pode ser maior do que a largura de banda, nesse caso a lentidão das respostas pode estar relacionada a isso e não tanto a lentidão do sistema.



# Pesquisa MQTT Broker AmazonMQ - Apache ActiveMQ e RabbitMQ

### Apresentação da aplicação

O objetivo dessa pesquisa é descobrir diferentes Broker MQTTs para avaliação do melhor para a nossa aplicação.
Nessa pesquisa será apresentado um recurso exclusivo da amazon, o AmazonMQ, serviço gerenciado agente de mensagens para o Apache ActiveMQ e o RabbitMQ que facilita a configuração e operação dos agentes de mensagens.

**Principais diferenças entre Apach ActiveMQ e RabbitMQ**

| Categoria                | Apache ActiveMQ                                                                                                                                                    | RabbitMQ                                                                                                                                                            |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Linguagem de programação | Totalmente escrito em Java.                                                                                                                                        | Módulos escritos em linguagem Erlang ou OTP.                                                                                                                        |
| Princípio de trabalho    | O ActiveMQ é usado em projetos corporativos para armazenar várias instâncias e suporta ambientes de cluster com base na especificação do sistema de mensagens JMS. | RabbitMQ é um mediador de mensagens que é executado no protocolo AMQP de baixo nível e atua como um intermediário entre duas aplicações no processo de comunicação. |
| Ferramentas usadas       | O ActiveMQ é um intermediário de mensagens com suporte para vários protocolos.                                                                                     | RabbitMQ HTTP funciona no plugin de gerenciamento.                                                                                                                  |
| Padrões de mensagens     | Os padrões de mensagens do ActiveMQ incluem PUB-SUB e fila de mensagens.                                                                                           | Os padrões gerais de mensagens do RabbitMQ incluem Fila de Mensagens, PUB-SUB e RPC e Roteamento.                                                                   |

## Escalabilidade

O RabbitMQ funciona com base no raio central/hub, o que torna esta abordagem única. RabbitMQ é muito portátil e fácil de usar. Isso ocorre porque as principais ações, como balanceamento de carga ou enfileiramento de mensagens persistentes, são executadas apenas em uma linha de código limitada. Essa abordagem, infelizmente, é mais lenta e menos escalável devido à latência adicionada do nó central e ao tamanho do envelope da mensagem.

Em comparação, o ActiveMQ é mais fácil de implementar e fornece recursos avançados como clustering, cache, log e armazenamento de mensagens.

## Integrabilidade

O RabbitMQ tem muitas vantagens que suportam vários protocolos de mensagens, reconhecimento de entrega e fila de mensagens. Ele é habilitado com várias linguagens, como Python, .NET e Java. Também pode ser usado com aplicativos como Chef, Docker e Puppet. Ele oferece alta taxa de transferência e disponibilidade desenvolvendo clusters. Ele pode suportar nuvem pública e privada com autenticação e autorização conectáveis. O HTTP-API é uma ferramenta de linha de comando e sua interface de usuário é útil no gerenciamento e monitoramento do broker RabbitMQ.

## Eficiência

O ActiveMQ possui várias vantagens que podem ser aplicadas para ter alta eficiência de acordo com o requisito. O RabbitMQ suporta C, C++, .NET e Python, sendo possível incorporar aplicativos multiplataforma pelo Advanced Message Queuing Protocol. Tem a flexibilidade de trocar mensagens entre aplicações web por STOMP que é o Streaming Text Oriented Messaging Protocol. Ele também programado para gerenciar dispositivos IoT.

## Quando usar o ActiveMQ vs. RabbitMQ

O RabbitMQ se destaca na implementação de um único corretor (rápido e rápido) e normalmente é usado para cenários simples. Possui uma arquitetura de plugins que permite arquiteturas complexas.

O ActiveMQ negocia uma pequena quantidade de velocidade para oferecer suporte nativo a arquiteturas e clientes complexos de rede multibroker usando uma grande variedade de protocolos. Ele vem junto com o Camel (que pode ser executado no corretor ou autônomo) para oferecer suporte a um grande número de padrões de integração empresarial.

## Conclusão da pesquisa MQTT Broker Apache ActiveMQ e RabbitMQ

Tanto o ActiveMQ quanto o RabbitMQ são soluções de mensagens confiáveis ​​e de alto desempenho com filosofias e pontos fortes ligeiramente diferentes. No entanto, é importante entender suas habilidades exclusivas antes de usá-las em ambientes de produção.

O RabbitMQ é executado no protocolo AMQP, para utilizar o protocolo MQTT ele necessita de um Plugin.

RabbitMQ é ideal para implantação baseada em erlang enxuta e confiável e se destaca para clientes de protocolo AMQP.

Em um experimento feito pelo site de como o melhor Broker [AutSoft](<https://autsoft.net/choosing-an-mqtt-broker-for-your-iot-project/>) foi relatado que "O problema com o RabbitMQ é o próprio suporte ao MQTT. Este broker suporta o protocolo AMQP nativamente, a implementação do MQTT está faltando alguns recursos importantes, como QoS2. O nível de qualidade de serviço 2 garante que uma mensagem seja recebida exatamente uma vez. Isso é muito importante em alguns casos, por exemplo, quando os comandos são enviados da plataforma IoT para os dispositivos ou atuadores. Comandos perdidos ou duplicados podem causar sérios problemas nesses cenários, portanto, QoS2 é essencial." Logo, ainda não é completo.

O ActiveMQ se destaca em integrações corporativas complexas e é baseado em JMS, integrando-se também a uma ampla variedade de sistemas por meio de seu extenso suporte de protocolo nativo e permitindo integrações adicionais por meio do Camel quando necessário. O ActiveMQ funciona bem em cenários de agente único, mas também oferece suporte a uma ampla variedade de arquiteturas mais complexas, conforme necessário. Porém ele ofereçe algumas desvantagens, segundo o site <https://cloudinfrastructureservices.co.uk/rabbitmq-vs-activemq/> Contras do ActiveMQ Message Broker:
Falta de garantia da entrega das mensagens.
As mensagens devem ser enviadas para filas ou tópicos.
Documentação inconveniente.
Não muito amigável para os usuários não-apache.

O RabbitMQ é mais eficiente que o ActiveMQ por causa de intermediários limitados. O ActiveMQ suporta a arquitetura Multi broker que às vezes leva tempo para processar uma mensagem.

Por fim, conclui-se que esse não seria o melhor serviço para MQTT Broker para a aplicação a ser desenvolvida, porque o RabbitMQ não oferece o recurso QoS2 e o ActiveMQ não garante a entrega das mensagens.

## Referências bibliográficas

<https://www.openlogic.com/blog/activemq-vs-rabbitmq#:~:text=ActiveMQ%20is%20used%20in%20enterprise,application%20in%20the%20communication%20process.>  
<https://hevodata.com/learn/rabbitmq-vs-activemq/>  
<https://autsoft.net/choosing-an-mqtt-broker-for-your-iot-project/>  
<https://cloudinfrastructureservices.co.uk/rabbitmq-vs-activemq/>  

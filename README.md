# Sistema de Hidroponia com IoT e Monitoramento Remoto

## Resumo

Este projeto apresenta um sistema completo de hidroponia automatizada utilizando tecnologias de Internet das Coisas (IoT) e computação distribuída. O sistema integra sensores para monitoramento de pH, temperatura e umidade, com controle automatizado de bombas peristálticas e interface de usuário mobile para acompanhamento remoto.

## Arquitetura do Sistema

O sistema é composto por três principais componentes arquiteturais:

### 1. Hardware - ESP8266 e Sensores
- **Microcontrolador**: ESP8266 para conectividade Wi-Fi
- **Sensores**: Monitoramento de pH, temperatura e umidade
- **Atuadores**: Bombas peristálticas para correção automática de pH
- **Comunicação**: Protocolo MQTT para transmissão de dados

![Protótipo do Sistema](images/prototipo.jpeg)

### 2. Middleware - Servidor Java e ActiveMQ
- **Servidor de Aplicação**: Java com Spring Boot
- **Message Broker**: Apache ActiveMQ para gerenciamento de mensagens
- **Banco de Dados**: Armazenamento de dados históricos e configurações
- **APIs REST**: Interface para comunicação com aplicação mobile

### 3. Interface de Usuário - Aplicação Flutter
- **Framework**: Flutter para desenvolvimento multiplataforma
- **Funcionalidades**: Monitoramento em tempo real, histórico de dados, configuração de parâmetros
- **Conectividade**: AWS Message Queue para comunicação com o servidor

## Casos de Uso

O sistema atende aos seguintes casos de uso principais:

![Casos de Uso](images/Casos_de_Uso_Hidroponia1.1.png)

1. **Monitoramento de Parâmetros**: Acompanhamento contínuo de pH, temperatura e umidade
2. **Controle Automatizado**: Acionamento automático de bombas para correção de pH
3. **Configuração Remota**: Definição de parâmetros ideais através da aplicação mobile
4. **Geração de Relatórios**: Histórico de dados e análises de tendências
5. **Autenticação de Usuários**: Controle de acesso seguro ao sistema

## Modelagem do Sistema

### Diagrama de Classes
![Diagrama de Classes](images/Classes,%20Hidroponia.png)

### Modelo Entidade-Relacionamento
![Modelo ER](images/mer.png)

### Diagrama de Componentes
![Diagrama de Componentes](images/Componentes%20Class%20diagram.png)

## Fluxo de Dados

### Fluxograma do ESP8266
![Fluxograma ESP8266](images/fluxograma-esp8266-completo.png)

O microcontrolador ESP8266 opera em um ciclo contínuo de:
1. Coleta de dados dos sensores
2. Processamento e validação dos dados
3. Envio via MQTT para o servidor
4. Recepção de comandos de controle
5. Acionamento de atuadores quando necessário

## Diagramas de Sequência

### Envio de Dados
![Sequência - Envio de Dados](images/sequencia1%20envio-de-dados.png)

### Alteração de Parâmetros
![Sequência - Alteração](images/sequencia2%20alteracao.png)

### Processo de Login
![Sequência - Login](images/sequencia3%20login.png)

### Geração de Relatórios
![Sequência - Relatórios](images/sequencia4%20relatorio.png)

## Tecnologias Utilizadas

### Hardware
- **ESP8266**: Microcontrolador com Wi-Fi integrado
- **Sensor de pH**: Monitoramento da acidez da solução nutritiva
- **Sensor de Temperatura**: Controle térmico do ambiente
- **Sensor de Umidade**: Monitoramento da umidade relativa
- **Bomba Peristáltica**: Dosagem precisa de soluções corretivas

![Bomba Peristáltica](images/bomba-peristaltica.png)
![Sensor de pH](images/sensor%20ph.jpg)

### Software
- **Linguagem C++**: Programação do microcontrolador ESP8266
- **Java**: Desenvolvimento do servidor de aplicação
- **Spring Boot**: Framework para desenvolvimento de APIs REST
- **Apache ActiveMQ**: Message broker para comunicação assíncrona
- **Flutter**: Framework para desenvolvimento da aplicação mobile
- **AWS Message Queue**: Serviço de mensageria na nuvem

### Protocolos e Comunicação
- **MQTT**: Protocolo de comunicação IoT
- **HTTP/HTTPS**: Comunicação REST entre aplicação e servidor
- **Wi-Fi**: Conectividade do microcontrolador
- **JSON**: Formato de dados para intercâmbio de informações

## Arquitetura de Implantação

![Diagrama de Implantação](images/implantacao.png)

A arquitetura de implantação contempla:
- **Camada de Sensores**: Dispositivos físicos no ambiente de cultivo
- **Camada de Conectividade**: Rede Wi-Fi para comunicação
- **Camada de Processamento**: Servidor Java e message broker
- **Camada de Apresentação**: Aplicação mobile Flutter
- **Camada de Persistência**: Banco de dados para armazenamento

## Funcionalidades Implementadas

### Monitoramento em Tempo Real
- Coleta contínua de dados dos sensores
- Transmissão automática via MQTT
- Visualização em tempo real na aplicação mobile

### Controle Automatizado
- Acionamento automático de bombas peristálticas
- Correção automática de pH baseada em parâmetros configurados
- Logs de todas as ações executadas

### Interface de Usuário
- Dashboard com indicadores visuais
- Histórico de dados com gráficos
- Configuração de parâmetros ideais
- Sistema de notificações para alertas

![Tela da Aplicação 1](images/print1.png)
![Tela da Aplicação 2](images/print2.png)

### Relatórios e Análises
- Geração de relatórios periódicos
- Análise de tendências dos parâmetros
- Exportação de dados históricos
- Alertas configuráveis por faixas de valores

## Instalação e Configuração

### Pré-requisitos
- Java 8 ou superior
- Apache ActiveMQ
- Flutter SDK
- Arduino IDE para programação do ESP8266

### Servidor Java
1. Extrair o arquivo `servidorJava.zip`
2. Configurar as credenciais do banco de dados
3. Executar o servidor Spring Boot

### Aplicação Flutter
1. Clonar o repositório: `https://github.com/MarceloRobert/aws_mq_app`
2. Inserir o arquivo `credentials.dart` na pasta `lib`
3. Configurar as variáveis de ambiente necessárias
4. Executar o comando `flutter run`

### Hardware ESP8266
1. Extrair o arquivo `esp8266-hidroponic-activemq-main.zip`
2. Configurar as credenciais Wi-Fi
3. Configurar os parâmetros de conexão MQTT
4. Fazer upload do código para o ESP8266

## Resultados Esperados

O sistema proporciona:
- **Automatização**: Redução da intervenção manual no cultivo
- **Monitoramento**: Acompanhamento contínuo dos parâmetros essenciais
- **Otimização**: Melhoria na qualidade e produtividade do cultivo
- **Controle Remoto**: Acesso ao sistema de qualquer local via aplicação mobile
- **Histórico**: Análise de dados para otimização contínua do processo

## Considerações Técnicas

### Escalabilidade
O sistema foi projetado para suportar múltiplas unidades de cultivo, com arquitetura modular que permite expansão horizontal.

### Segurança
Implementação de autenticação e autorização para controle de acesso, com comunicação segura entre os componentes.

### Manutenibilidade
Código organizado em camadas bem definidas, com documentação técnica e comentários explicativos.

### Disponibilidade
Arquitetura distribuída com tolerância a falhas e mecanismos de recuperação automática.

## Conclusão

Este projeto demonstra a aplicação prática de conceitos de sistemas distribuídos e IoT em um domínio real da agricultura urbana. A integração de tecnologias modernas permite criar um sistema eficiente, escalável e de fácil utilização para automação de cultivos hidropônicos.

A solução apresentada oferece uma base sólida para futuras expansões e melhorias, contribuindo para a modernização da agricultura e otimização dos recursos utilizados no cultivo de plantas.

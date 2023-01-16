
## Acesso Remoto Seguro

Acesso remoto seguro é a combinação de métodos de segurança e tecnologias que permitem que entidades externas se conectem as redes, sem comprometer ativos digitais ou expor redes à partes não autorizadas.

#### Métodos de Acesso Seguro Mais Comuns

- IPsec VPN (Internet Protocol Security Virtual Private Network) - protege a camada de rede do Modelo OSI
- SSL VPN (Secure Socket Layer Virtual Private Network) - protege da camada de transporte até a camada de aplicação
- ZTNA (Zero Trust Network Acess) - protege da camada de transporte até a camada de aplicação

**ZTNA**

O ZTNA estabelece uma sessão segura entre uma entidade final e uma rede, enquanto garante controle granular sobre o acesso a recursos e exerce confiança zero.

- Zero trust -> acesso de privilégio mínimo
- Túnel criptografado automaticamente
- Controle de acesso dinamico

##### Como Funciona o Fortinet ZTNA

**Passo 1 - Validação de Identidade do Dispositivo**
- O endipoint conecta ao proxy de acesso ZTNA
- FortiGate "desafia" o endpoint para identificação do dispositivo
- O endpoint envia o certificado do dispositivo para o FortiGate, que foi emitido pelo FortiClient EMS
- O FortiGate aplica as tags e as regras associadas ao dispositivo

**Passo 2 - Autenticação do Usuário**
- FortiGate consulta o endpoint para autenticação do usuário
- O usuário insere suas credenciais no endpoint
- O FortiGate encaminha as credenciais para o servidor de autenticação, que pode ser um AD, um diretório LDPA, um banco de dados ou Identity-as-a-Service (IDaaS)
- A identidade do usuário é validada e a função do usuário é recuperada do servidor de autenticação
- A funçao de usuário é usada pelo FortiGate para determinar o acesso para o aplicativo de rede

**Passo 3 - Sessão Criptografada Estabelecida**


#### Secure Access Service Edge - SASE

Combina as tecnologias de Network-as-a-Service com Security-as-a-Service incluindo:

**Emparelhamento**
- Possibilita a conexão de rede e a troca de tráfego diretamente pela internet sem a necessidade de pagar para terceiros

**Firewall de próxima geração NGFW ou FWaaS**
- Firewall como serviço em nuvem
- Com recursos como IPS, Anti-Malware, Inspeção SSL e Área restrita

**Secure Web Gateway**
- Filtrando o malware
- Aplicando políticas de segurança da internet e de conformidade

**Zero Trust Network Access - ZTNA**
- Nenhum usuário ou dispositivo seja considerado confiável automaticamente
- Cada tentativa de acessas o sistema é desafiada e verificada
- Diversas tecnologias como Autenticação multifator (MFA), Controle de acesso à rede (NAC) e Aplicação de políticas de acesso

**Prevenção contra perda de dados DLP**
- Impede que os usuários finais movam informações para fora da rede
- Inspeção de conteúdo das aplicações de mensagens e e-mail

**Sistema de nomes de domínio DNS**
- Funciona como uma lista telefônica da internet
- Proporciona ao SASE os recursos de detecção de ameaças
- Analisa e avalia domínios perigosos

O objetivo do SASE é atender às atuais necessidades de acesso seguro e dinâmico das organizações. Com um bom serviço de SASE, as organizações podem ampliar a segurança e redes corporativas para: 
- A borda da nuvem, com o acesso de usuários remotos, de fora da rede; e
- A borda fina, como filiais pequenas

A solução de SASE em nuvem da Fortinet é o FortiSASETM


## Sugurança na Nuvem

**Infraestrutura como Serviço ou IaaS**

A IaaS fornece às organizações 
- rede,
- armazenamento,
- servidores físicos e
- virtualização

Enquanto os usuários ainda devem disponibilizar
- computadores com sistemas operacionais, 
- middleware, 
- dados e aplicações. 

Middleware é um software que atua como uma ponte entre o sistema operacional e as aplicações. Uma organização usa esse tipo de serviço quando a demanda por seus serviços ou produtos varia, como durante feriados sazonais, quando as cargas de trabalho nos sistemas aumentam.

**Platform as a Service ou PaaS**

Fornece o sistema operacional e o middleware, além dos elementos fornecidos pelo IaaS. Esse serviço torna mais fácil, mais eficiente e mais barato para as organizações construírem, testarem e implantarem aplicações.

**Software as a Service ou SaaS**

Normalmente, o usuário final se conecta à aplicação usando seu navegador. Exemplos comuns de aplicações disponíveis por meio de SaaS são Google Mail, Salesforce, DocuSign e Netflix.

#### Proteção

Do ponto de vista da segurança, o fornecedor é responsável apenas por proteger a infraestrutura que fornece. Como cliente, quando você instala um ou mais aplicativos virtualizados na infraestrutura de nuvem do fornecedor, você se torna responsável por proteger o acesso, o tráfego de rede e os dados dos aplicativos.


## SD-WAN

SD-WAN significa rede de longa distância definida por software ou, em inglês, software-defined wide-area network, e aprimora o corporativo WAN, bem como conectividade em várias nuvens, para oferecer desempenho de aplicativos em alta velocidade.

No geral, os resultados positivos de uma solução SD-WAN segura são simplificação, consolidação e redução de custos, ao mesmo tempo em que fornecem ótimo desempenho de aplicativos e a melhor experiência do usuário para os aplicativos corporativos, SaaS e Comunicações Unificadas como Serviço (UCaaS).


## Endpoint Security

No passado, o termo **endpoint** era definido como um dispositivo pessoal utilizado por um usuário final, como um computador desktop, laptop ou dispositivo portátil. Agora, os endpoints também abrangem os dispositivos da Internet das Coisas (IoT), como um termostato inteligente ou uma geladeira doméstica.

Os primeiros produtos de segurança de endpoints foram os antivírus (AV). Eles funcionavam com base em assinatura, ou seja, o software antivírus buscava características especificas (impressões digitais ou assinaturas) do vírus.

Uma nova estratégia para proteger os endpoints foi criada em conjunto com o desenvolvimento da EPP. Essa nova estratégia é chamada de detecção e resposta de endpoints (EDR).

EDR é um software utilizado para detectar, investigar e responder às atividades suspeitas nos endpoints.

Os produtos de segurança de Endpoint Fortinet são FortiClient® e FortiEDRTM. O Endpoint que executa o FortiClient® é totalmente integrado a outros produtos de segurança que compartilham dados de inteligência e são gerenciados centralmente no que é chamado de Fortinet Security Fabric. O produto de detecção e resposta estendido Fortinet é FortiXDRTM.


## Firewall

Os firewalls de 1ª geração utilizavam **filtros de pacotes** que examinavam as camadas de protocolo mais baixas, como endereços de rede de origem e destino, protocolos e números de porta. A desvantagem dos firewalls com filtros de pacotes era que eles adotavam uma abordagem genérica para decidir se o tráfego seria permitido ou não, e os malfeitores conseguiam burlar as regras dos firewalls.

Os firewalls de2ª geração, chamados firewalls com **monitoramento de estado**, foram criados para observar essas conexões de rede ao longo do tempo. Eles monitoravam como as novas conexões eram feitas e analisavam continuamente a interação entre os endpoints. Mas os firewalls de segunda geração ainda não conseguiam bloquear pacotes nocivos que utilizavam protocolos aceitáveis, como HTTP.

Para determinar como protocolos como o HTTP são utilizados, o firewall precisa analisar as cargas de dados de uma forma mais detalhada. 

É exatamente isso que os firewalls de 3ª geração fazem. Apesar de continuarem oferecendo monitoramento de estado, esses firewalls compreenderam os protocolos de nível superior e os aplicativos inclusos neles, e controlaram os diferentes usos do mesmo protocolo básico. Isso é denominado **filtragem de camadas do aplicativo**.

Os firewalls de hoje precisam impedir os crescentes ataques virtuais em cada borda da rede e, ao mesmo tempo, proporcionar segurança, confiabilidade e desempenho de rede. Isso é o que vemos nos recursos avançados de segurança dos firewalls de última geração (NGFW). Eles possuem a capacidade de controlar aplicativos por classificação ou de acordo com o usuário e também adotaram várias abordagens de segmentação que isolam usuários, dispositivos e aplicativos, se alinhando às necessidades dos negócios.

#### Firewalls de última geração (NGFW)

Três características:

- Pode segmentar uma rede com base no usuário, dispositivo e tipo de aplicativo
- Controla aplicativos com base no tipo ou quem é o usuário
- Oferece inspeção de alto desempenho

O FortiGate® é o firewall de última geração da Fortinet. O dispositivo FortiGate® possui integração total com outros produtos de segurança que compartilham dados de informações e são gerenciados de maneira centralizada no Fortinet Security Fabric.


## Wi-fi

Wi-Fi é a tecnologia para Wireless, local area networking de dispositivos com base no padrão IEEE 802.11. O desenvolvimento do Wi-Fi aproveitou muitos dos mesmos protocolos e tecnologia da Ethernet, com uma grande diferença. Todas as transmissões estão acontecendo no ar.

Originalmente, os mecanismos de autenticação e privacidade para Wi-Fi eram muito fracos. O padrão tinha uma opção simples de fornecer criptografia chamada Wired Equivalent Privacy WEP.

Um novo padrão, com base no Advanced Encryption Standard AES, algoritmo do National Institute of Standards and Technology NIST, foi introduzido como Wi-Fi Protected Access 2 WPA2. Além disso, uma nova autenticação de nível empresarial foi adicionada à tecnologia, criando dois tipos de cada estilo de segurança. O nível de segurança pessoal continuou a usar uma frase-senha compartilhada para autenticação de rede e troca de senha. O nível de segurança empresarial usa mecanismos de autenticação 802.1x, semelhantes aos usados em redes com fio, para autenticar usuários e configurar a criptografia. No entanto, frases-senha mal escolhidas ou fracas ainda podem deixar as redes vulneráveis.

Lançado em 2018, Wi-Fi Protected Access 3 (WPA3) introduziu um handshake novo e mais seguro para fazer conexões, um método mais fácil para adicionar dispositivos à rede, tamanhos de chave aumentados e outros recursos de segurança.

A Fortinet oferece um produto sem fio denominado FortiAP™. Ele é compatível com as tecnologias Wi-Fi mais recentes, se integra e é gerenciado pelo FortiGate®, um firewall de última geração.


## Threat Intelligence Services

1ª geração: Catálogo de assinaturas de virus. Essas listas de assinaturas de vírus eram distribuídas com o software antivírus. Conforme novos vírus eram detectados, o serviço de informações contra ameaças de cada fornecedor distribuía atualizações à lista de assinaturas de vírus.

#### Malware polimórfico

Família completa de malware, que pode ter centenas de milhares de arquivos diferentes devido a capacidade de alterar o conteúdo do arquivo conforme fosse necessário. Como o conteúdo do arquivo é alterado, suas assinaturas também mudam.

#### Detecção heurística

Coloca o arquivo suspeito em um ambiente onde é possível analisar detalhadamente os comportamentos que ele apresenta. Se o arquivo tiver algum comportamento malicioso dentro do sandbox, ele será identificado como malware.

**Sandbox** - A sandbox funciona como um ambiente virtual independente do seu computador e da sua rede, utilizado para testar, executar e bloquear programas e códigos potencialmente maliciosos. 

Além do sandbox, o futuro da detecção prévia de malware desconhecido também conta com o uso de inteligência artificial e aprendizado de máquina pelos serviços de informações contra ameaças para classificar com rapidez o potencial de ameaça à segurança dos arquivos transferidos na rede.


O serviço de informações contra ameaças da Fortinet se chama FortiGuard® Labs


## SOAR

A SOAR conecta todas as outras ferramentas da sua pilha de segurança formando fluxos de trabalho definidos, que podem ser executados automaticamente. Em outras palavras, a SOAR aumenta a eficiência da sua equipe automatizando processos manuais repetitivos.

Por exemplo, na SOAR, é possível bloquear tráfego de um endereço IP malicioso em seu firewall ou excluir um e-mail de phishing do seu servidor de e-mail

Recursos fundamentais:

- Orquestração e automatização
- Investigação

As investigações de phishing são um dos casos de uso mais comuns para a implementação da SOAR pelos clientes. Sem a SOAR, um analista passaria muito tempo investigando o remetente de um e-mail de phishing e os principais indicadores localizados no cabeçalho ou no corpo do e-mail.

Nessas investigações, normalmente é preciso inserir domínios e URLs em uma plataforma de informações sobre ameaças. Se os analistas determinarem que o e-mail é prejudicial, terão de gastar mais tempo para investigar o servidor de e-mail e o SIM, determinar quem recebeu o e-mail e quem clicou nele, excluí-lo etc. Com um guia estratégico de investigação de phishing, as medidas de investigação iniciais são tomadas automaticamente assim que o e-mail de phishing for denunciado.

O produto de SOAR da Fortinet se chama FortiSOAR™


## Controle de Acesso à Rede (NAC)

O NAC (Netwoork Access Control) é um dispositivo ou uma máquina virtual que controla o acesso de dispositivos à rede. Ele segmenta uma rede utilizando perfis do dispositivo.

De acordo com os padrões IEEE 802.1X três partes participam da autenticação de rede:

- Autenticador
- Servidor de autenticação
- Dispositivo cliente

Atualmente as soluções NAC têm visibilidade completa da rede e são melhores em categorizar dispositivos automaticamente. Elas apresentam um bom desempenho em redes Ethernet e sem fio. Muitas soluções de NAC têm uma arquitetura centralizada que melhora o controle dos dispositivos em redes grandes e com locais distribuídos. É fundamental que o NAC também seja integrado à estrutura de segurança para que, quando uma violação for detectada, o NAC responda automaticamente para notificar a central de operações de segurança (SOC) e funcione em conjunto com outros dispositivos de segurança para neutralizar a ameaça.

A Fortinet oferece uma solução de controle de acesso à rede chamada FortiNAC™.


## Sandbox

Um sandbox, no contexto de segurança da computação, é um sistema que limita as ações de um aplicativo, como abrir um documento ou um browser, a um ambiente virtual isolado. Com esse ambiente virtual seguro, o sandbox estuda as várias interações do aplicativo para descobrir qualquer intenção maliciosa.

Os Sandbox mais modernos possuem recursos de automação e inteligência artificial

O produto Sandbox Fortinet é denominado chamado FortiSandbox ™

**MITRE ATT&CK** é uma estrutura, um conjunto de matrizes de dados e uma ferramenta de avaliação desenvolvida pela MITRE Corporation para ajudar as organizações a entender sua preparação para segurança e descobrir vulnerabilidades em seus métodos de defesa. 

À medida que novas vulnerabilidades e superfícies de ataque surgem, elas são adicionadas à estrutura ATT&CK, que está em constante evolução.
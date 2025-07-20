# Desvendando os Logs: Os Olhos e Ouvidos da Segurança Cibernética

Os **Logs** são a base da segurança cibernética, funcionando como os alicerces de uma casa. Sem eles, a estrutura da nossa defesa estaria comprometida.

Em um avião, temos o que chamamos de **Diário de Bordo**. Basicamente, ele registra cada ação da aeronave, seja algo que ocorreu com sucesso ou que falhou. Logs são exatamente como um diário de bordo digital: são **registros detalhados de eventos e ações**, sejam elas bem-sucedidas ou não.

## O Que é um Log?

Como mencionei com a analogia do avião, um log, em sua essência, é um **registro digital de eventos**. Pense nele como um histórico detalhado de tudo o que acontece em um sistema. Vou explicar melhor com um exemplo prático:

* Você liga o computador: *bip!* Temos um log!
    * **Log:** `computador iniciado 12:00 12/03/2025`
* Você quer navegar na internet, clica no ícone: *bip!* Temos outro log!
    * **Log:** `navegador iniciado 12:20 12/03/2025`
* Você acessa o Google no navegador, e adivinha? *Bip!* Mais um log!
    * **Log:** `seu ip 192.xxx.xxx.xx conectando a google.com`

Cada ação dentro de um dispositivo ou software gera e armazena um log, contendo diversos detalhes sobre a ação: quem fez, para onde, se deu certo, se falhou, o horário e muito mais.

## Qual a Importância dos Logs na Segurança Cibernética?

Imagine um alarme de porta. Tenho um desses em todas as portas que abrem aqui em casa. Adivinha o que ele faz? Exato: gera logs! Toda vez que dispara, ele gera um log; se falha, também gera. Se ele não gerar nada, como eu saberia que alguém tentou abrir minha porta, ou que alguém abriu ontem? Eu preciso desses logs para armazenar as informações essenciais.

Agora que você já entendeu o conceito, vamos focar na importância dos logs na cibersegurança:

### 1. Registro de Atividades

Como você já sabe, o log armazena tudo o que acontece, e isso é extremamente útil. Já pensou estar monitorando tudo e, de repente, descobrir que uma máquina está infectada com um vírus? Meu Deus! Mas de onde esse vírus veio? Você acessa a máquina, verifica os logs dela e descobre que o usuário clicou em um arquivo chamado `souumvirusdomal.exe`. Opa, acho que temos um suspeito!

### 2. Detecção de Ameaças

Eu meio que expliquei isso no exemplo acima, mas vamos detalhar mais. No item 1, vimos que os logs são importantes porque registram tudo. Aqui, o foco são os registros de ameaças ou tentativas de ameaça. Você está monitorando tranquilamente e percebe que um IP desconhecido, por exemplo, da Índia, está tentando acessar seu servidor. Você consegue verificar tudo isso por meio de vários logs de tentativas falhas de acesso, indicando uma possível atividade maliciosa.

### 3. Investigação de Incidentes (Forensics)

Basicamente, um item complementa o outro, mas aqui os logs te ajudam a ir mais fundo. Em uma investigação forense, sem os logs, você estaria perdido! Não teríamos os rastros do agente malicioso. Você não saberia quais passos ele tomou e, assim, não conseguiria prever os próximos.

Observe o nível de importância de uma empresa ter um sistema que monitora os logs e uma equipe treinada: se a empresa não se preocupa com a segurança, um agente malicioso pode acessar, se infiltrar e permanecer ali por semanas, meses ou até anos, sem NINGUÉM saber de nada!

### 4. Conformidade e Auditoria

Como eu disse no item 3, uma empresa sem registro de logs pode estar até fora da lei! Por quê? Muitas regulamentações, como a **LGPD** no Brasil ou a **GDPR** na Europa, exigem que as empresas mantenham registros detalhados das atividades. Se uma empresa possui logs, isso já é um ponto importante que demonstra a conformidade. Porque se não há logs, meu Deus, o primeiro pilar da CIA (Confidencialidade, Integridade e Disponibilidade) já está comprometido! Desse jeito, a empresa não passaria por uma auditoria.

Vou dar um exemplo: o Banco Central tem empresas terceirizadas que o auxiliam em alguns setores. Para essas empresas serem contratadas, elas precisam estar em total conformidade. No caso de não possuírem armazenamento de registros digitais (logs), elas simplesmente não seriam aprovadas.

### 5. Melhoria Contínua

Quanto mais registros temos, melhor a segurança se torna com o passar do tempo. Por quê? Basicamente, podemos identificar diariamente possíveis falhas nos logs, às vezes até vulnerabilidades. Podemos perceber, por exemplo, que um usuário básico que tinha acesso somente ao estoque, de repente, acessou o setor financeiro. Oxi?! Mas nós havíamos criado toda uma estrutura em nosso sistema relacionada ao princípio do menor privilégio! Por que cargas d'água o "Zezinho" acessou o financeiro? Pronto! Com o log, identificamos uma falha no sistema que precisa ser corrigida!

## Fontes Comuns de Logs (Os Observadores da Sua Rede)

Temos três fontes comuns de logs essenciais:

### 1. Logs de Firewall

Primeiro, o que é um firewall? Hmm, vou te explicar:
Imagine um castelo mágico. Nele, o rei colocou um porteiro que encontrou nas Florestas dos Vulcões. Esse porteiro decide quem entra e quem sai. O rei estabeleceu regras com ele e pediu para ele registrar quem entrou, e quem tentou entrar. Se o príncipe um dia tentar fazer uma ligação para um "serviço de fadas" que não é para maiores de 18 anos, e o rei já disse ao nosso porteiro (o firewall) que isso não pode entrar, quando as fadas tentarem passar, o firewall fechará os tijolos e ligará o fogo ao redor dele!

Mas na vida real, o que um firewall registra? Basicamente, ele registra informações relevantes sobre as tentativas de conexão, como:
- IP de origem e destino
- Portas utilizadas
- Protocolos (TCP ou UDP)
- Se a conexão foi bem-sucedida ou não
- O horário do evento

Exemplo de log de firewall:
`192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO OK | 23:00 12/03/2027`

Se você for uma pessoa curiosa, deve estar se perguntando: por que isso é importante?
Você consegue ver quem está tentando entrar e para onde seus dados estão indo. Pense que você está monitorando os logs e vê isso:

192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO FALHADA | 23:00 12/03/2027
192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO FALHADA | 23:00 12/03/2027
192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO FALHADA | 23:00 12/03/2027
192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO FALHADA | 23:00 12/03/2027
192.168.234.12 | 193.23.23.43 | 80 | TCP | CONEXAO FALHADA | 23:00 12/03/2027

Um IP suspeito tentando conexão várias vezes sem parar! Aí você pega o IP, joga em uma ferramenta que armazena IPs suspeitos e *voilà*! Você descobre que há uma tentativa maliciosa desse IP e pode configurar o firewall para bloqueá-lo.

Outro exemplo real de log de firewall:
`20/07/2025 16:50 pop-os kernel [ 5946.470690] [UFW AUDIT] IN=wlxdc4ef402f30a OUT= MAC=dc:4e:f4:02:f3:0a:5c:c9:d3:02:b5:8f:08:00 SRC=192.168.0.23 DST=192.168.0.10 LEN=84 TOS=0x00 PREC=0x00 TTL=64 ID=23119 DF PROTO=ICMP TYPE=8 CODE=0 ID=3 SEQ=10`

Fiz um ping do meu PC Kali (IP `192.168.0.23`) para meu PC com Pop!_OS (IP `192.168.0.10`), e esse foi o log. Repare no `PROTO` (protocolo), que indica `ICMP` (no caso, um ping). Ele também mostra a data e que o `UFW` (nosso firewall) está em modo `AUDIT`, uma ação neutra: nem permitindo, nem bloqueando, é como se estivesse apenas "dando uma olhada".

### 2. Logs de Rede

Os logs de rede, diferente do nosso porteiro mágico (o firewall) que verifica apenas quem entra ou quem sai da fronteira do castelo, verificam tudo o que está acontecendo **dentro da rede**, incluindo conexões internas. Pense nele como o mordomo do nosso castelo: ele é responsável por ver quem entra e quem sai, auxiliando o porteiro mágico, mas também cuida das comunicações internas do castelo, como entre os hóspedes, o rei, e até leva recados do príncipe para a rainha e tudo mais.

Então, se você manda um pacote de um PC com Windows para um PC Mac na mesma rede interna, quem vai registrar isso são os logs da rede, e não o firewall.

Detalhando um pouco mais sobre o que os logs de rede registram:
Ele registra quem está conectado à rede. Imagine um `nmap` que você consegue ver todo mundo que está na rede; os logs de rede armazenam todas essas informações. Com um `Wireshark`, você consegue ver o uso de banda larga, erros de conexões e muito mais, como portas, IPs, tipos de conexões e eventos dos roteadores.

Ele é tão importante quanto os logs do firewall. Você vai identificar tentativas de conexões estranhas, pacotes saindo que não deveriam. Digamos que você esteja monitorando os logs da rede e, de repente, vê um dispositivo que você nunca viu, não sabe como foi parar ali, e do nada você começa a receber logs desse dispositivo tentando se comunicar com outros dispositivos na rede. Suspeito, não é?

### 3. Logs de Servidor

Servidores são como os cérebros de muitas operações, como sites, arquivos, e-mails, bancos de dados, entre outros. Logs de servidores são basicamente os registros de tudo o que acontece dentro dos servidores.

Ele registra tudo, certo? Então teremos tentativas de login, manipulação de arquivos, entradas e saídas, falhas, uso de recursos de hardware e atividades dos serviços.

A importância dos logs de servidor segue a mesma linha dos outros tipos de logs: conseguimos ver se tudo está funcionando como deveria, ou se tem algum "engraçadinho" mexendo onde não deve, seja alguém interno ou algum agente malicioso externo.

## Como os Logs de Firewall Diferem dos Logs de Rede?

Podemos descrever a diferença usando nossa história encantada:

O **Firewall** é nosso porteiro. Ele cuida de toda a fronteira do castelo, decidindo quem pode entrar e quem pode sair. Se há invasores do lado de fora do castelo, ele não vai deixá-los entrar. Mas se é o rei tentando entrar após uma viagem de batalha, nosso "muralhão" vai deixá-lo passar. Também serve para o caso de o príncipe estar de castigo: se o rei disse que ele não pode sair, o firewall não permitirá. Em resumo, o firewall monitora e controla o tráfego que entra e sai da rede, ou seja, as **conexões de fronteira**.

Já nossos **Logs de Rede**, nosso querido mordomo, cuidam de **tudo o que está dentro do castelo**. Ele registra se os empregados estão trabalhando, se o príncipe fez a lição de casa, e registra até a conversa do jardineiro com o mecânico. Ou seja, os logs de rede monitoram e registram as **comunicações internas** entre os dispositivos da rede, além de fornecer uma visão mais ampla do tráfego geral.

---

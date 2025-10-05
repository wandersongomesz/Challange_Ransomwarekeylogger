<h1>Simulação Educacional: Ransomware & Keylogger — Modo Seguro</h1>

**Autor:** Wanderson Gomes<br>
**Data:** 2025-10-03

**Aviso importante:** Este repositório contém simulações educacionais destinadas a demonstrar conceitos de ataque e defesa. Não há código malicioso executável aqui. Não execute nada fora de um ambiente controlado (máquina virtual isolada ou contêiner com volume restrito). Leia tudo antes de rodar qualquer arquivo.

<h1>Objetivo</h1>

Fornecer um projeto didático que:

* Demonstra o fluxo e o impacto conceitual de um ransomware e de um keylogger;
* Ensina como simular e testar cenários de ataque em modo seguro;
* Documenta medidas práticas de detecção, prevenção e resposta. <br>

Este repositório foca em educação e defesa — as implementações são deliberadamente inofensivas e projetadas para operar somente dentro de um diretório sandbox e em modo --dry-run.

<h1>Estrutura do repositório</h1>

````
/ 
├─ MALWARES/             # Scripts e resultado e arquivos da simulação
│   ├─ teste_files       # Diretorio de arquivos que foram usados
│   │   ├─ dados_confidenciais.txt 
│   │   └─ senhas.txt 
│   ├─ ransomware.py 
│   ├─ descriptografar.py 
│   ├─ chave.key <br>     # Chave de criptografia para exercicio de simnulação 
│   └─ LEIA ISSO.TXT <br>     # Mensagem informativa de encritação dos dados afetados 
├─ KEYLOGGER/             # Scripts de simulação
│   ├─ keylogger.pyw <br>    # Codigo de escuta e captura de caracteres do teclado, extesão ".pyw" para rodar em segundo plano. 
│   ├─ keylogger_email.py    # Codigo que encia tudo que foi coletado por email.
│   └─ log.txt <br>          # Arquivo que armazena todas as informações coletadas.
├─ images/                   # Imagens dos com o resultado dos testes
└─ README.md <br>
````
<h1>Aviso de Ética e Legalidade</h1>

Não publique, distribua ou execute rotinas que capturem teclas, exfiltrarem dados, ou encriptem arquivos em sistemas de produção ou de terceiros sem consentimento explícito e documentado.
Execute demonstrações somente em VMs isoladas ou contêineres com snapshots e sem acesso à rede de produção.
Se você for aluno/funcionário, obtenha autorização por escrito antes de realizar qualquer teste em infra de terceiros.


<h1>O Que os Scripts fazem:</h1>

**MALWARE** <BR>
* percorrem apenas os arquivos dentro de ./MALWARES/tetes_file e critografa os arquivos com a chave que foi gerada; <BR>
* criam um arquivo LEIA ISSO.txt dentro do ./MALWARES com texto explicativo, informando que o dado foi criptografado;  <BR>
* no aruivo ./descritografar.py é realizado a descriptação do arquivo baseado na chave que foi gerada.  <BR>
 
**KEYLOGGER** <BR>
* executa o codigo em segundo plano para escutar e gravar tudo que for digitado;  <BR>
* cria um arquivo log.txt, onde são armazenadas todas as capturas de tecla;  <BR>
* enciar email a cada 60 segundo com as informações capturadas.  <BR>

<h1>Medidas de detecção, prevenção e resposta</h1>

* **EDR/Antivírus:** monitoramento de comportamento — detecção de padrões como renomeação em massa, cifragem em sequência, criação de notas de resgate. <BR>
* **Backup imutável e offsite:** políticas de retenção e recuperação testadas.  <BR>
* **Restrição de privilégios:** minimizar contas com permissão de escrita ampla e admins rotativos.  <BR>
* **Segmentação de rede e filtragem:** controle de saída para impedir exfiltração.  <BR>
* **DLP:** regras para monitorar movimentação de dados sensíveis.  <BR>
* **Conscientização:** treinamentos de phishing e respostas a incidentes.  <BR>
* **SIEM:** coleta centralizada de logs e correlação de eventos.


<h1>OBRIGADO!</h1>

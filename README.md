# Cidadania-Ativa: o chatbot que facilita o acesso a informação
## Introdução: apresentação do projeto
O acesso à informação é essencial para o exercício da cidadania, mas muitos cidadãos, especialmente os mais vulneráveis, enfrentam dificuldades para encontrar e compreender dados sobre benefícios públicos, que hoje estão dispersos em diferentes sites, escritos em linguagem técnica e envoltos em burocracia. Para solucionar essa barreira, o projeto Cidadania Ativa propõe a criação de um chatbot integrado ao WhatsApp que utiliza inteligência artificial para centralizar e simplificar essas informações, facilitando o entendimento dos direitos disponíveis, promovendo autonomia ao cidadão e fortalecendo a relação entre a população e o poder público.

## Tecnologias 

### Inteligência Artificial e Processamento de Linguagem
-  Gemini (Modelo de Inteligência Artificial): Atuou como o núcleo cognitivo do chatbot. É responsável por processar as entradas textuais dos usuários e gerar respostas em linguagem natural. O modelo é acessado por meio da API Gemini.
   * Nota: Inicialmente, o projeto utilizou a versão gratuita do Gemini, mas devido a limitações (como o número de tokens e capacidade de resposta), foi migrado para a versão paga para garantir maior estabilidade e qualidade.
-  Processamento de Linguagem Natural (PLN): Essencial para que o chatbot entenda as intenções e as perguntas dos usuários.
- System Messages: Utilizadas para o sistema de refinamento das perguntas do usuário, reorganizando, contextualizando e simplificando a questão antes de enviá-la ao agente de IA.
- Base de Conhecimento Oficial: A base de informações usada pelo chatbot foi construída exclusivamente a partir de pesquisas em sites oficiais de órgãos públicos, garantindo a precisão e a confiabilidade das informações sobre benefícios federais.
### Plataformas de Interação e Automação
- WhatsApp: Selecionado como o canal oficial de interação e a interface de comunicação com os usuários, devido à sua ampla adoção pela população.
- N8N: Ferramenta de automação (ou orquestração de fluxos) que coordena o processamento do sistema. É responsável por gerenciar o recebimento de mensagens, aplicar condições lógicas, integrar com o modelo de IA e enviar as respostas.
- Evolution API: Usada para conectar o chatbot ao WhatsApp, permitindo o envio e recebimento de mensagens de forma automatizada e escalável, intermediando a comunicação entre o WhatsApp e o n8n via webhooks. Essa ferramenta foi escolhida por oferecer mais funcionalidades do que alternativas anteriores, como o Waha.
- Webhooks e APIs REST: Mecanismos de comunicação utilizados para que os componentes do sistema (WhatsApp, Evolution API, n8n, Gemini) se comuniquem e formem uma cadeia contínua e automatizada.
### Infraestrutura e Dados
- Redis (Base de Dados Temporária): Utilizado para o armazenamento temporário do contexto da conversa e interações, permitindo consultas rápidas e mantendo a coerência do diálogo por um período limitado (TTL de 48 horas).
- Hostinger: Servidor onde os serviços próprios do sistema (n8n, Evolution API e Redis) são hospedados, funcionando como o servidor principal da aplicação.
- Docker: Utilizado na fase inicial e de prototipação do projeto, em conjunto com n8n, Redis e Waha, para a execução local do sistema.
- Google Forms: Utilizado para coletar feedback dos usuários após o encerramento das conversas, servindo como insumo para o aprimoramento do sistema.
### Metodologia de Desenvolvimento
- Modelo Metodológico Híbrido: O desenvolvimento do sistema integrou o framework Scrum com técnicas de priorização da Matriz de Eisenhower. Essa abordagem foi escolhida para garantir flexibilidade, ciclos contínuos de refinamento e gestão eficiente das prioridades.

## Demosntração


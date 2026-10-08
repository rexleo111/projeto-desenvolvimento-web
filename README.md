# [Nome do Projeto]

> Substitua os trechos entre colchetes `[ ]` pelas informações reais do trabalho. Remova esta nota e as demais orientações em *itálico* antes da entrega.

[![Status](https://img.shields.io/badge/status-[em_desenvolvimento]-yellow)]()
[![Versão](https://img.shields.io/badge/versão-[0.1.0]-blue)]()
[![Licença](https://img.shields.io/badge/licença-[acadêmica]-lightgrey)]()

**Instituição:** Centro Universitário de Brasília (UniCEUB)<br>
**Curso:** Ciência da Computação<br>
**Disciplina:** Desenvolvimento Web<br>
**Turma / Semestre:** 2026.2<br>
**Professor(a):** Felippe Pires Ferreira<br>
**Status do projeto:** Em desenvolvimento<br>

---

## Sumário

- [1. Descrição do projeto](#1-descrição-do-projeto)
- [2. Funcionalidades](#2-funcionalidades)
- [3. Demonstração](#3-demonstração)
- [4. Tecnologias utilizadas](#4-tecnologias-utilizadas)
- [5. Arquitetura](#5-arquitetura)
- [6. Organização dos diretórios](#6-organização-dos-diretórios)
- [7. Participantes](#7-participantes)
- [8. Como executar](#8-como-executar)
- [9. Configuração](#9-configuração)
- [10. Testes](#10-testes)
- [11. Uso de inteligência artificial](#11-uso-de-inteligência-artificial)
- [12. Contribuição e fluxo de trabalho](#12-contribuição-e-fluxo-de-trabalho)
- [13. Histórico de versões](#13-histórico-de-versões)
- [14. Limitações e próximos passos](#14-limitações-e-próximos-passos)
- [15. Licença, referências e contato](#15-licença-referências-e-contato)

---

## 1. Descrição do projeto

Instituições de ensino frequentemente enfrentam desafios na centralização e digitalização do acompanhamento acadêmico. A gestão manual ou fragmentada de diários de classe, notas, frequências e materiais didáticos gera inconsistências de dados, atraso na comunicação entre a coordenação, docentes e discentes, e sobrecarga administrativa.

O Sistema de Gestão Escolar surge para unificar esses fluxos, automatizando processos operacionais e provendo interfaces dedicadas para cada perfil de usuário.

A implementação de uma solução web desenvolvida em Python com o ecossistema Django oferece alta produtividade, robustez em segurança e facilidade de manutenção.

### Objetivos

- **Objetivo geral:** desenvolver uma aplicação web de gestão escolar utilizando Python e Django.
- **Objetivos específicos:**
  - Oferecer autenticação e autorização por perfil (Aluno, Professor e Coordenação), de modo que cada usuário acesse apenas os módulos permitidos.
  - Permitir que a Coordenação cadastre, edite e inative usuários, organize turmas (disciplinas, professores e horários), matricule alunos e emita relatórios de rendimento escolar.
  - Permitir que o Professor visualize suas turmas e alunos, registre frequência por aula, lance e atualize notas e registre observações pedagógicas.
  - Permitir que o Aluno consulte o boletim atualizado, o percentual de frequência por disciplina, a grade horária e as disciplinas matriculadas.
  - Disponibilizar uma API REST própria para consulta de dados de turmas, alunos e notas.
  - Integrar uma API externa de consulta de CEP para preencher automaticamente o endereço no cadastro de usuários.

### Público-alvo

- **Alunos:** estudantes matriculados que precisam acompanhar seu desempenho acadêmico e boletins.
- **Professores:** corpo docente responsável pelo lançamento de avaliações, frequências e observações pedagógicas.
- **Coordenação pedagógica/administrativa:** gestores responsáveis pela estrutura curricular, pelas turmas e pelas matrículas.

---

## 2. Funcionalidades

| Funcionalidade | Casos de uso | Descrição | Status |
| --- | --- | --- | --- |
| Autenticação por perfil | UC01 | Login com direcionamento ao portal do perfil (Aluno, Professor ou Coordenação) e bloqueio de áreas de outros perfis | Planejada |
| Boletim escolar | UC02 | Consulta de notas, médias e frequência por disciplina, sempre atualizadas | Planejada |
| Consulta de frequência | UC03 | Percentual de frequência do aluno por disciplina | Planejada |
| Grade horária e disciplinas | UC04, UC05 | Consulta da grade horária e das disciplinas em que o aluno está matriculado | Planejada |
| Alunos da turma | UC06 | Lista de turmas e alunos sob responsabilidade do professor | Planejada |
| Registro de frequência | UC07 | Chamada por aula, com presença ou ausência de cada aluno | Planejada |
| Lançamento de notas | UC08 | Registro e atualização de notas parciais e finais | Planejada |
| Observações pedagógicas | UC09 | Registro de observações do professor sobre o aluno | Planejada |
| Cadastro de usuários | UC10, UC11, UC12 | Cadastro de alunos, professores e coordenadores | Planejada |
| Manutenção de usuários | UC13, UC14 | Edição e inativação de usuários (sem exclusão, para preservar o histórico) | Planejada |
| Cadastro de disciplinas | UC15 | Cadastro das disciplinas oferecidas | Planejada |
| Organização de turmas | UC16 | Criação de turmas e alocação de disciplinas, professores e horários | Planejada |
| Matrícula | UC17 | Matrícula de alunos ativos em turmas ativas | Planejada |
| Relatório de rendimento | UC18 | Relatório consolidado de médias e frequência dos alunos de uma turma | Planejada |
| API REST própria | Sem caso de uso | Endpoints autenticados para consulta de dados de turmas, alunos e notas (Django REST Framework) | Planejada |
| Consulta de CEP (API externa) | Sem caso de uso | Preenchimento automático do endereço no cadastro de usuários a partir do CEP | Planejada |

### Requisitos não funcionais

- **Plataforma:** o sistema deve ser desenvolvido em Python 3.x com o framework Django.
- **Persistência:** banco de dados relacional SQLite.
- **Interoperabilidade:** a API REST própria deve seguir os padrões REST, com uso correto dos verbos HTTP e dos códigos de status.
- **Segurança:** os dados de entrada devem ser validados no servidor, as senhas devem ser armazenadas com hash e o acesso aos módulos deve ser restrito ao perfil do usuário.
- **Configuração:** chaves, credenciais e demais configurações sensíveis devem ficar em variáveis de ambiente, fora do código versionado.
- **Usabilidade:** a interface deve ser responsiva e funcionar em navegadores web modernos, no computador e no celular.
- **Disponibilidade:** o sistema deve ser publicado em ambiente acessível pela internet, com acesso via HTTPS.

---

## 3. Demonstração

*Inclua capturas de tela, GIF ou link para vídeo. Coloque as imagens em `images/`.*

![Tela principal](images/[screenshot-principal].png)

| Tela | Descrição |
| --- | --- |
| [Login] | [Acesso ao sistema com e-mail e senha] |
| [Painel] | [Visão geral das reservas do dia] |

**Vídeo / protótipo:** [URL do YouTube, Loom ou Figma]

---

## 4. Tecnologias utilizadas

*Informe as tecnologias de fato usadas no projeto. Remova as linhas que não se aplicarem.*

| Camada | Tecnologia | Versão |
| --- | --- | --- |
| Linguagem | [Ex.: Python, Java, TypeScript] | [Ex.: 3.12] |
| Frontend | [Ex.: HTML, CSS, React] | [Ex.: 18] |
| Backend | [Ex.: Flask, Spring Boot, Node.js] | [Ex.: 3.x] |
| Banco de dados | [Ex.: PostgreSQL, SQLite, MongoDB] | [Ex.: 16] |
| Testes | [Ex.: pytest, JUnit, Jest] | [Ex.: 8] |
| Infraestrutura | [Ex.: Docker, GitHub Actions] | — |
| Outras ferramentas | [Ex.: Git, Figma, Postman] | — |

---

## 5. Arquitetura

O sistema segue uma arquitetura web cliente-servidor construída com Django. A ideia é separar a interface, as regras de negócio e o armazenamento dos dados.

### Componentes

| Componente | Função |
| --- | --- |
| Cliente (navegador web) | Telas por onde Alunos, Professores e Coordenação usam o sistema. |
| Servidor de aplicação (Django) | Recebe os pedidos, verifica o perfil do usuário e aplica as regras de negócio. |
| Banco de dados (SQLite) | Guarda os dados do sistema. |
| Serviço externo (API ViaCEP) | Devolve o endereço a partir do CEP informado no cadastro. |

### Camadas do Django

- **Models:** representam as classes do domínio (Usuario, Turma, Matricula, Nota etc.) e fazem o acesso ao banco.
- **Views:** recebem as requisições, checam as permissões e aplicam as regras de negócio.
- **Templates:** montam as páginas HTML que o navegador exibe.
- **Django REST Framework:** expõe parte dos dados em formato JSON pela API REST própria.

### Como funciona

1. O usuário acessa uma tela pelo navegador.
2. O Django recebe o pedido, confere se o perfil tem permissão e executa a regra de negócio.
3. Quando precisa, o Django lê ou grava os dados no banco SQLite.
4. O Django devolve uma página HTML (telas) ou um JSON (API REST).
5. No cadastro de usuário, o navegador consulta a API ViaCEP com o CEP digitado e preenche o endereço automaticamente.

Diagrama de implantação: [`docs/arquitetura/diagrama-implantacao.pdf`](docs/arquitetura/diagrama-implantacao.pdf)

### Decisões relevantes

- **Django REST Framework** para construir a API REST própria.
- **SQLite** como banco de dados, por ser simples de configurar.
- **Inativar em vez de excluir:** usuários e turmas são inativados, para preservar o histórico de notas e frequências.
- **Média e frequência calculadas:** os valores são calculados a partir das notas e chamadas registradas, sem guardar o resultado no banco.

### API externa

- **Serviço:** ViaCEP.
- **Finalidade:** preencher automaticamente o endereço (logradouro, bairro, cidade e estado) no cadastro de usuários, a partir do CEP. Esses dados correspondem à classe Endereco do diagrama de classes.
- **Plano de integração:** [a definir]

### Endpoints principais

O contrato da API ainda está em definição. Os endpoints abaixo são o ponto de partida previsto no Documento de Visão.

| Método | Rota | Descrição |
| --- | --- | --- |
| `GET` | `/api/v1/turmas/` | Lista as turmas e seus dados |
| `GET` | `/api/v1/boletim/` | Consulta o boletim do aluno (notas, médias e frequência) |

Documentação completa da API: [a definir]

---

## 6. Organização dos diretórios

```text
.
├── README.md                                       # Documentação principal do projeto
├── docs/                                           # Documentação de análise e modelagem
│   ├── visao/
│   │   └── documento_de_visao.md                   # Documento de Visão
│   └── modelagem/
│       ├── casos-de-uso/
│       │   ├── Especificacoes-casos-de-uso.docx.pdf  # Catálogo, diagrama e especificações
│       │   └── Diagrama de caso de uso gest escolar  # Fonte editável do diagrama (draw.io)
│       ├── classes/
│       │   ├── diagrama-classes.docx.pdf           # Diagrama, responsabilidades e relacionamentos
│       │   └── diagrama_classesv2.jpg              # Imagem do diagrama de classes
│       └── banco-de-dados/
│           ├── diagrama-er.pdf                     # Modelo conceitual (em elaboração)
│           └── modelo-logico.pdf                   # Modelo lógico (em elaboração)
└── images/
    └── semaforo.png                                # Figura da política de uso de IA
```

| Diretório | Função |
| --- | --- |
| `docs/visao/` | Documento de Visão: contexto, objetivos, escopo, restrições e riscos |
| `docs/modelagem/casos-de-uso/` | Especificações dos casos de uso e fonte editável do diagrama |
| `docs/modelagem/classes/` | Diagrama de classes do domínio |
| `docs/modelagem/banco-de-dados/` | Modelo de dados do sistema |
| `images/` | Figuras da documentação geral do repositório |

---

## 7. Participantes

| Nome | Matrícula | Função no projeto |
| --- | --- | --- |
| João Gabriel Torres | 22503395 | [Ex.: coordenação / backend / frontend / testes / documentação] |
| João Vitor Mendes Peres | 22503802 | [Ex.: backend] |
| Leonardo Cespedes Paes Huard | 22505698 | [Ex.: frontend] |

**Professor(a) responsável:** Felippe Pires Ferreira

---

## 8. Como executar

*Preencha com os comandos reais do projeto para que outra pessoa consiga reproduzir o ambiente.*

### Pré-requisitos

- [Ex.: Git]
- [Ex.: Python 3.12+]
- [Ex.: Node.js 20+]
- [Ex.: Docker]

### Instalação e execução

```bash
# 1. Clonar o repositório
git clone https://github.com/rexleo111/projeto-desenvolvimento-web.git
cd [NOME_DA_PASTA]

# 2. Instalar dependências
[comando de instalação]

# 3. Configurar variáveis de ambiente
cp .env.example .env
# edite o arquivo .env com as credenciais locais

# 4. Executar a aplicação
[comando de execução]
```

**Acesso local:** [Ex.: http://localhost:3000]

### Implantação (quando houver)

- **Ambiente:** [Ex.: Render, Railway, Vercel, servidor da instituição]
- **URL de produção:** [https://...]
- **Observações:** [Ex.: é necessário configurar as variáveis de ambiente no painel do provedor]

---

## 9. Configuração

*Liste as variáveis de ambiente usadas pelo sistema. Nunca publique senhas, tokens ou chaves neste arquivo.*

| Variável | Obrigatória | Descrição | Exemplo |
| --- | --- | --- | --- |
| `PORT` | Sim | Porta da aplicação | `3000` |
| `DATABASE_URL` | Sim | Conexão com o banco | `postgresql://user:senha@localhost:5432/app` |
| `SECRET_KEY` | Sim | Chave de sessão / JWT | `[gerar localmente]` |

Credenciais reais devem ficar apenas no arquivo `.env` (não versionado).

---

## 10. Testes

*Descreva como executar os testes e o que eles cobrem.*

```bash
[comando para executar os testes]
```

| Tipo | Ferramenta | O que verifica |
| --- | --- | --- |
| Unitários | [Ex.: pytest / JUnit / Jest] | [Ex.: regras de negócio isoladas] |
| Integração | [Ex.: ...] | [Ex.: API e banco de dados] |
| Manuais | [Ex.: checklist em `docs/`] | [Ex.: fluxos principais da interface] |

**Cobertura atual:** [Ex.: 70% / não medida]

---

## 11. Uso de inteligência artificial

Este repositório segue a política de uso de IA da disciplina (semáforo pedagógico):

![Política de uso de IA — semáforo](images/semaforo.png)

| Situação | Significado |
| --- | --- |
| **Vermelho — uso proibido** | Atividades de autonomia intelectual (ex.: provas presenciais sem consulta). |
| **Amarelo — uso limitado** | IA pode ser ferramenta auxiliar, desde que haja declaração de uso. |
| **Verde — uso permitido** | Uso livre ao longo da atividade acadêmica. |

### Declaração de uso

*Preencha de forma honesta. Se não houve uso de IA, declare explicitamente.*

- **Houve uso de IA neste projeto?** [Sim / Não]
- **Ferramentas utilizadas:** [Ex.: ChatGPT, GitHub Copilot, Gemini — ou “nenhuma”]
- **Finalidade:** [Ex.: revisão de texto, geração de esboço de testes, esclarecimento de dúvidas de sintaxe]
- **O que NÃO foi delegado à IA:** [Ex.: definição do problema, modelagem, implementação das regras de negócio, testes finais]

---

## 12. Contribuição e fluxo de trabalho

*Padronize o trabalho em equipe. Ajuste as regras ao combinado da disciplina.*

### Branches

- `main` — versão estável para avaliação
- `develop` — integração do grupo *(opcional)*
- `feat/[nome]` — nova funcionalidade
- `fix/[nome]` — correção de defeito
- `docs/[nome]` — alterações só de documentação

### Commits

Use mensagens curtas e no imperativo, por exemplo:

- `feat: adiciona cadastro de reservas`
- `fix: corrige validação de data`
- `docs: atualiza instruções de execução`

### Passos sugeridos

1. Criar uma branch a partir de `main`.
2. Implementar e testar localmente.
3. Abrir um *pull request* / *merge request* para revisão do grupo.
4. Só então integrar à branch principal.

**Issues e quadro de tarefas:** [link do GitHub Projects, Trello ou similar]

---

## 13. Histórico de versões

| Versão | Data | Descrição |
| --- | --- | --- |
| `0.0.2` | 08/10/2026 | Preenchimento inicial do README |
| `0.0.1` | 07/10/2026 | Estrutura inicial do repositório |

---

## 14. Limitações e próximos passos

### Problemas conhecidos

- [Ex.: a recuperação de senha ainda não envia e-mail]
- [Ex.: o layout quebra em telas menores que 360 px]

### Roadmap

- [ ] [Ex.: autenticação com dois fatores]
- [ ] [Ex.: exportação de relatórios em CSV]
- [ ] [Ex.: implantação em ambiente de homologação]

---

## 15. Licença, referências e contato

**Licença:** uso exclusivamente acadêmico.

Este material destina-se a fins educacionais. Verifique com a disciplina se o código pode ser reutilizado fora do curso.

### Documentação complementar

- Documento de Visão: [`docs/visao/documento_de_visao.md`](docs/visao/documento_de_visao.md)
- Casos de uso (catálogo, diagrama e especificações): [`docs/modelagem/casos-de-uso/Especificacoes-casos-de-uso.docx.pdf`](docs/modelagem/casos-de-uso/Especificacoes-casos-de-uso.docx.pdf)
- Diagrama de casos de uso (fonte editável, draw.io): [`docs/modelagem/casos-de-uso/Diagrama de caso de uso gest escolar`](<docs/modelagem/casos-de-uso/Diagrama de caso de uso gest escolar>)
- Diagrama de classes: [`docs/modelagem/classes/diagrama-classes.docx.pdf`](docs/modelagem/classes/diagrama-classes.docx.pdf)
- Imagem do diagrama de classes: [`docs/modelagem/classes/diagrama_classesv2.jpg`](docs/modelagem/classes/diagrama_classesv2.jpg)

### Referências

- Django Software Foundation. Documentação do Django. Disponível em: <https://docs.djangoproject.com/>.
- ViaCEP. Webservice gratuito de consulta de CEP. Disponível em: <https://viacep.com.br/>.

### Contato

Dúvidas sobre o projeto: [e-mail institucional do grupo ou issue no repositório]

**Agradecimentos:** [Ex.: professor(a), monitoria, materiais da disciplina]

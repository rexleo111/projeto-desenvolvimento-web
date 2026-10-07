# Documento de Visão
## Sistema de Gestão Escolar (SGE)

---

## 1. Contexto e Problema
Instituições de ensino frequentemente enfrentam desafios na centralização e digitalização do acompanhamento acadêmico. A gestão manual ou fragmentada de diários de classe, notas, frequências e materiais didáticos gera inconsistências de dados, atraso na comunicação entre a coordenação, docentes e discentes, e sobrecarga administrativa.

O Sistema de Gestão Escolar surge para unificar esses fluxos, automatizando processos operacionais e provendo interfaces dedicadas para cada perfil de usuário.

## 2. Justificativa
A implementação de uma solução web desenvolvida em Python com o ecossistema Django oferece alta produtividade, robustez em segurança e facilidade de manutenção.

## 3. Objetivos
- Desenvolver uma aplicação web de gestão escolar utilizando Python e Django.

## 4. Público-alvo
- **Alunos:** Estudantes matriculados que necessitam acompanhar seu desempenho acadêmico e boletins.
- **Professores:** Corpo docente responsável pelo lançamento de avaliações, frequências e conteúdos ministrados.
- **Coordenação Pedagógica/Administrativa:** Gestores responsáveis pela manutenção da estrutura curricular e matrículas.

## 5. Stakeholders

| Papel                         | Descrição                             | Responsabilidade no Projeto 

| **Coordenação**               | Gestores do ambiente escolar          | Validação de regras de negócio, cadastro de turmas e controle de acessos. 
| **Professores**               | Usuários operacionais docentes        | Lançamento diário de notas, faltas e plano de ensino. 
| **Alunos**                    | Usuários finais de consulta           | Acesso a boletins, histórico de frequência e avisos. 
| **Equipe de Desenvolvimento** | Desenvolvedores Web (Python/Django)   | Modelagem, implementação da API REST, integrações e interface gráfica. 

## 6. Escopo
O projeto abrange as seguintes entregas funcionais e técnicas:
- Módulo de autenticação e autorização por perfil (Group/Permissions do Django).
- Painel administrativo e operacional para a Coordenação (CRUD de cursos, disciplinas, turmas, alunos e professores).
- Portal do Professor para gestão de diário de classe (notas e frequências).
- Portal do Aluno para consulta de boletim, índice de assiduidade e matérias.
- **API REST Própria:** Endpoints protegidos para exposição de dados de turmas, alunos e notas (usando Django REST Framework).
- **Integração Externa:** Consumo de serviço web via API para preenchimento automático de endereço de alunos (ViaCEP) ou consulta de feriados acadêmicos (Brasil API).

## 7. Itens fora do Escopo
- Módulo de gestão financeira ou emissão de boletos bancários.
- Acesso dedicado para pais/responsáveis nesta primeira versão.
- Sistema de fórum de discussão ou chat em tempo real.

## 8. Funcionalidades

### 8.1. Módulo Coordenação
- Cadastrar, editar e inativar usuários (Alunos, Professores, Coordenadores).
- Criar e estruturar turmas, alocando disciplinas e professores responsáveis.
- Realizar a matrícula de alunos em turmas ativas.
- Emitir relatórios gerais de rendimento escolar.

### 8.2. Módulo Professor
- Visualizar a lista de turmas e alunos sob sua responsabilidade.
- Registrar e atualizar notas parciais e finais.
- Registrar chamadas/frequências por aula ministrada.
- Inserir observações pedagógicas por aluno.

### 8.3. Módulo Aluno
- Visualizar o boletim escolar atualizado em tempo real.
- Acompanhar o percentual de frequência por disciplina.
- Consultar a grade horária e as disciplinas matriculadas.

### 8.4. Serviços de API
- **API REST Interna:** Endpoints `/api/v1/boletim/`, `/api/v1/turmas/` para consumo de dados estruturados.
- **Consumo de API Externa:** Consulta automatizada de CEP para validação cadastral de endereços dos usuários.

## 9. Restrições
- O sistema deve ser desenvolvido obrigatoriamente utilizando a linguagem **Python 3.x** e o framework **Django**.
- A API REST própria deve seguir os padrões arquiteturais REST (utilização correta dos verbos HTTP e códigos de status).
- O banco de dados relacional deve ser o **SQLite** (para ambiente de desenvolvimento) ou **PostgreSQL**.
- A interface gráfica deve ser responsiva e acessível via navegadores web modernos.

## 10. Premissas
- Os usuários possuem acesso regular à internet e a navegadores web atualizados.
- A coordenação fornecerá as regras de transição de ano letivo, cálculo de médias e limite de faltas para reprovação.
- As APIs externas utilizadas para integração estarão disponíveis e operacionais durante o período de desenvolvimento e testes.

## 11. Riscos Iniciais

| Risco                                     | Impacto   | Mitigação 

| **Indisponibilidade da API externa**      | Médio     | Implementar rotinas de fallback e validações manuais de dados. 
| **Complexidade nas permissões do Django** | Média     | Definir matriz de acessos detalhada antes do desenvolvimento das views. 
| **Atraso na modelagem do Banco de Dados** | Alto      | Realizar reuniões de alinhamento estrutural logo no início do projeto. 
| **Incompatibilidade de CORS na API REST** | Baixo     | Configurar adequadamente o pacote `django-cors-headers`. 

## 12. Critérios de Sucesso
- Todos os perfis (Aluno, Professor, Coordenação) conseguem autenticar-se e visualizar exclusivamente os módulos permitidos.
- O cálculo de médias e a consolidação de frequências funcionam sem divergências matemáticas.
- A API REST própria responde com sucesso (status HTTP 200/201) para requisições autenticadas.
- A integração com a API externa realiza o preenchimento de dados cadastrais corretamente sem travar o fluxo principal da aplicação.
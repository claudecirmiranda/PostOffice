# Especificação do Aplicativo Post Office

## Sumário Executivo

Este documento consolida a especificação completa do aplicativo Post Office, incluindo histórias de usuário, estrutura de backlog e planejamento de incrementos. O aplicativo visa modernizar e digitalizar os serviços postais, permitindo que clientes finais gerenciem contas, comprem etiquetas de postagem, rastreiem encomendas e localizem agências de forma prática e eficiente.

---

## 1. Histórias de Usuário

### US01 - Criar Conta de Cliente

**Persona:** Cliente final

**Capacidade:** Criar uma conta informando nome, endereço, e-mail, celular e preferências de marketing.

**Benefício:** Permitir acesso personalizado e seguro aos serviços de postagem e rastreamento.

**Critérios de Aceitação:**

1. **Dado que** o cliente não possua uma conta  
   **Quando** preencher e submeter o formulário de cadastro com todos os dados obrigatórios  
   **Então** a conta do cliente é criada e o acesso ao app é liberado

2. **Dado que** haja campos obrigatórios não preenchidos  
   **Quando** o cliente tentar submeter o cadastro  
   **Então** o sistema exibe mensagens de erro informando quais campos devem ser preenchidos

3. **Dado que** o cliente opte por receber comunicações de marketing  
   **Quando** o cadastro for completado  
   **Então** a preferência é registrada junto à conta do cliente

---

### US02 - Editar Dados Pessoais

**Persona:** Cliente final

**Capacidade:** Editar dados pessoais e preferências de marketing na conta.

**Benefício:** Permitir atualização de informações e controle de consentimento para comunicações.

**Critérios de Aceitação:**

1. **Dado que** o cliente esteja logado  
   **Quando** acessar a opção de edição de conta e alterar os dados  
   **Então** as alterações são salvas e refletidas no perfil

2. **Dado que** o cliente atualize a preferência de marketing  
   **Quando** salvar as alterações  
   **Então** a nova preferência é registrada

---

### US03 - Comprar Etiquetas de Postagem

**Persona:** Cliente final

**Capacidade:** Comprar etiquetas de postagem com opção de entrega em agência.

**Benefício:** Facilitar o envio de objetos postais de forma prática e eficiente.

**Critérios de Aceitação:**

1. **Dado que** o cliente escolha comprar uma etiqueta de postagem  
   **Quando** preencher as informações de envio e destinatário  
   **Então** o sistema apresenta opções de entrega, incluindo entrega em agência

2. **Dado que** a etiqueta esteja paga  
   **Quando** o cliente optar pela entrega em agência  
   **Então** a etiqueta é emitida habilitando a postagem presencial

---

### US04 - Gerar QR Code para Postagem

**Persona:** Cliente final

**Capacidade:** Gerar um QR Code para postagem física no balcão da agência após a compra da etiqueta.

**Benefício:** Agilizar e simplificar o processo de postagem presencial nas agências.

**Critérios de Aceitação:**

1. **Dado que** uma etiqueta de postagem para entrega em agência seja adquirida  
   **Quando** o cliente acessar a opção de postagem presencial  
   **Então** é gerado um QR Code válido para apresentação no balcão

2. **Dado que** o cliente esteja offline  
   **Quando** acessar a funcionalidade de QR Code de uma etiqueta já emitida  
   **Então** o QR Code é exibido mesmo sem conexão

---

### US05 - Rastrear Encomendas

**Persona:** Cliente final

**Capacidade:** Rastrear a situação de encomendas compradas via aplicativo.

**Benefício:** Permitir acompanhamento atualizado e transparente dos objetos postais.

**Critérios de Aceitação:**

1. **Dado que** o cliente possua encomendas cadastradas  
   **Quando** acessar a tela de rastreamento  
   **Então** o status atual de cada objeto é apresentado

2. **Dado que** o rastreamento esteja indisponível online  
   **Quando** o cliente tentar consultar status de uma encomenda  
   **Então** o último status sincronizado é exibido

---

### US06 - Buscar Agências Próximas

**Persona:** Cliente final

**Capacidade:** Buscar agências próximas, com exibição de informações detalhadas.

**Benefício:** Facilitar a localização de pontos de atendimento para postagem e retirada.

**Critérios de Aceitação:**

1. **Dado que** o cliente permita o uso de localização ou insira um endereço  
   **Quando** buscar agências  
   **Então** uma lista de agências próximas com detalhes como endereço, horário e serviços é exibida

2. **Dado que** o cliente não esteja conectado à internet mas buscou agências recentemente  
   **Quando** acessar o localizador  
   **Então** a última lista de agências pesquisada é apresentada

---

### US07 - Contatar Suporte

**Persona:** Cliente final

**Capacidade:** Entrar em contato com o suporte da Post Office pelo app via formulário ou visualizando detalhes de contato.

**Benefício:** Permitir o esclarecimento de dúvidas, acompanhamento de solicitações e suporte ágil.

**Critérios de Aceitação:**

1. **Dado que** o cliente navegue até a área de ajuda e suporte  
   **Quando** selecionar a opção formulário de contato  
   **Então** um formulário é exibido e pode ser enviado pelo aplicativo

2. **Dado que** o cliente prefira contato direto  
   **Quando** acessar detalhes de contato  
   **Então** informações como telefone e e-mail são apresentados

---

## 2. Sugestões de Testes

### 2.1 Testes Funcionais

- Verificar criação de conta com todos os campos obrigatórios preenchidos
- Validar edição e persistência das informações do perfil do cliente
- Testar fluxo completo de compra de etiqueta com seleção de entrega em agência
- Validar geração e leitura do QR Code após compra de etiqueta
- Testar rastreamento de diferentes objetos postais no app
- Verificar busca de agências por localização e exibição de informações corretas
- Submeter formulário de contato e conferir envio/support

### 2.2 Testes Não Funcionais

- Avaliar usabilidade e acessibilidade segundo padrões WCAG 2.1 e ABNT NBR 17060
- Testar funcionamento dos recursos essenciais em modo offline (offline-first)
- Executar testes de compatibilidade em múltiplos dispositivos Android e iOS
- Validar resiliência da geração e leitura de QR Code offline
- Realizar testes de integração com sistemas legados e serviços AWS
- Avaliar segurança de dados sensíveis conforme LGPD e PCIDSS
- Monitorar respostas do app sob cenários de falha de API ou conectividade

---

## 3. Feedback de Qualidade

### 3.1 Premissas

- Cada usuário possui uma única conta vinculada ao seu e-mail
- A preferência de marketing pode ser alterada a qualquer momento
- O histórico de agências pesquisadas e objetos rastreados é armazenado localmente para acesso offline

### 3.2 Questões em Aberto

- Qual o fluxo para exclusão de conta do cliente? Existe política de retenção de dados?
- Quais detalhes mínimos devem ser exibidos em agências (ex.: acessibilidade, serviços especializados)?
- O suporte via formulário é integrado a algum sistema de tickets/categorias?

### 3.3 Riscos Identificados

- A falha de integração com sistemas legados pode inviabilizar rastreamento ou atualização de status de objetos
- A ausência de conectividade pode dificultar a atualização das agências próximas ou status de rastreamento
- Mudança futura nas regras de privacidade pode impactar a coleta de informações no cadastro

---

## 4. Restrições Técnicas

- **Suporte Offline:** O aplicativo deve garantir o funcionamento básico sem conectividade (offline-first)
- **Acessibilidade:** Conformidade rigorosa com os padrões WCAG 2.1 e ABNT NBR 17060
- **Segurança e Compliance:** Arquitetura em conformidade com PCIDSS para pagamentos e aderência à LGPD/GDPR
- **Compatibilidade:** Obrigatória com sistemas operacionais Android e iOS
- **Integração:** Com infraestrutura AWS, sistemas legados via CloudFoundry PaaS e APIs dos Correios
- **Monitoramento:** Integração com SOC (Security Operations Center) e sistema ServiceNow para alertas operacionais

---

## 5. Estrutura do Backlog

### Epic E1: Gestão de Conta do Cliente

**Histórias:** US01, US02

**Justificativa:** As duas histórias tratam da criação, manutenção e atualização dos dados de conta do usuário, formando uma cadeia lógica de onboarding e gestão de informações do cliente no aplicativo.

---

### Epic E2: Postagem e Envio Multitransportadora

**Histórias:** US03, US04

**Justificativa:** Estas histórias habilitam o cliente a adquirir etiquetas de postagem, selecionar opções de entrega em agência e gerar QR Code para postagem física, contemplando todo o fluxo operacional de postagem presencial.

---

### Epic E3: Rastreamento de Encomendas

**Histórias:** US05

**Justificativa:** Esta história representa a funcionalidade separada e específica de rastrear objetos postais, essencial para a jornada após a postagem.

---

### Epic E4: Localização de Agências

**Histórias:** US06

**Justificativa:** A busca e exibição de agências constitui um agrupamento independente e central para apoiar serviços presenciais e tomada de decisão pelo cliente.

---

### Epic E5: Suporte e Atendimento ao Cliente

**Histórias:** US07

**Justificativa:** O contato com suporte e visualização de informações de atendimento são serviços transacionais que se concentram na solução de dúvidas do usuário final.

---

## 6. Dependências entre Histórias

### US02 → US01 (Sequencial)
Para editar dados do perfil, o cliente precisa necessariamente ter a conta criada. Logo, a funcionalidade de edição depende da existência e cadastro inicial da conta.

### US03 → US01 (Funcional)
A compra de etiqueta requer autenticação e gestão de informações do cliente, sendo dependente da existência de uma conta criada.

### US04 → US03 (Sequencial)
A geração de QR Code só é possível uma vez que a compra da etiqueta de postagem foi realizada.

### US05 → US03 (Dados)
A rastreabilidade de objetos só ocorre após a aquisição de uma etiqueta pelo aplicativo.

---

## 7. Priorização (Método MoSCoW)

| Story | Prioridade | Justificativa |
|-------|-----------|---------------|
| US01 | **Must Have** | O cadastro de conta é base para todas as demais funcionalidades que requerem identificação do usuário |
| US02 | **Should Have** | A edição de dados enriquece a experiência, mas não é bloqueadora do fluxo mínimo de uso da aplicação |
| US03 | **Must Have** | A aquisição de etiquetas é o core do negócio para o envio de encomendas via aplicativo, viabilizando as entregas |
| US04 | **Must Have** | A geração de QR Code é mandatória para permitir a postagem física no balcão, conforme requisito específico do contexto |
| US05 | **Must Have** | A rastreabilidade dos objetos é essencial para acompanhamento pós-venda, elevando transparência e valor percebido |
| US06 | **Should Have** | A busca de agências apoia fluxos presenciais, mas pode ser contingenciada por outros canais em um MVP inicial |
| US07 | **Should Have** | O suporte é importante para satisfação e resolução de dúvidas, mas não bloqueia o funcionamento core da solução |

---

## 8. Planejamento de Incrementos

### Incremento INC01: Onboarding e Autenticação

**Objetivo:** Habilitar onboarding e autenticação do cliente, estabelecendo a base de identidade e autorização para todas as funcionalidades subsequentes do aplicativo.

**Histórias:** US01

**Justificativa:** US01 é absolutamente foundational, bloqueando todas as demais capabilities que requerem identificação do cliente. Sua entrega isolada permite validação precoce de conformidade com LGPD/GDPR no cadastro e estabelece padrões de captura de consentimento que impactarão todo o sistema.

**Drivers Arquiteturais:**

- Autenticação e gestão de identidade: necessidade de escolha de mecanismo de autenticação (local, federada, token-based) que suporte offline-first
- Armazenamento seguro de credenciais e dados pessoais: conformidade PCI-DSS e LGPD/GDPR para dados sensíveis em repouso e em trânsito
- Sincronização de dados de perfil: estratégia de consistência eventual entre cliente mobile e backend em cenário de conectividade intermitente
- Gestão de consentimento: captura e rastreabilidade de opt-in/opt-out para marketing, essencial para compliance regulatório
- Criptografia de dados sensíveis: proteção de informações pessoais (e-mail, celular, endereço) tanto localmente quanto em transmissão

---

### Incremento INC02: Jornada Core de Postagem

**Objetivo:** Entregar a jornada core de postagem, desde compra de etiqueta até geração de QR Code para postagem física, viabilizando a proposta de valor central do aplicativo.

**Histórias:** US03, US04

**Justificativa:** US03 e US04 formam o fluxo atômico de postagem e representam o core business value. A dependência sequencial US03→US04 e a criticidade Must Have de ambas tornam este incremento indivisível. Sua entrega permite validação de market fit e geração de receita, justificando investimento em incrementos subsequentes.

**Drivers Arquiteturais:**

- Integração com múltiplas transportadoras: necessidade de camada de abstração para cálculo de frete, disponibilidade e SLA de diferentes provedores logísticos
- Motor de precificação: lógica de cálculo de custos considerando peso, dimensões, origem, destino e modalidade de entrega
- Geração e validação de QR Code: padrão de codificação, segurança criptográfica para prevenção de fraudes e resiliência offline
- Processamento de pagamentos: integração PCI-DSS compliant com gateway de pagamento, gestão de transações e reconciliação financeira
- Persistência offline de etiquetas e QR Codes: garantia de acesso a objetos comprados mesmo sem conectividade, com sincronização posterior de status
- Orquestração de transações distribuídas: coordenação entre pagamento, emissão de etiqueta e registro em sistemas legados via CloudFoundry

---

### Incremento INC03: Rastreamento de Objetos

**Objetivo:** Prover visibilidade e transparência pós-postagem através de rastreamento de objetos, aumentando confiança e reduzindo demanda de suporte.

**Histórias:** US05

**Justificativa:** US05 depende de dados gerados por US03 (dependência data) mas representa capability ortogonal à postagem, podendo ser desenvolvida após consolidação do incremento anterior. Sua classificação Must Have reflete criticidade para satisfação do cliente, mas não bloqueia a geração de receita inicial.

**Drivers Arquiteturais:**

- Integração com APIs de rastreamento: consumo de múltiplas fontes de tracking (Correios, transportadoras privadas) com normalização de status e eventos
- Polling vs Push: definição de estratégia de atualização de status (pull periódico, webhooks, server-sent events) balanceando latência e carga
- Cache e sincronização offline: armazenamento local de último status conhecido para exibição em cenário desconectado
- Notificações push: arquitetura para alertas proativos de mudança de status (em trânsito, entregue, tentativa de entrega)
- Resiliência a falhas de integração: circuit breakers, fallbacks e estratégias de retry para APIs externas instáveis ou indisponíveis

---

### Incremento INC04: Funcionalidades Complementares

**Objetivo:** Complementar a experiência com funcionalidades de suporte à jornada presencial e atendimento ao cliente, aumentando autonomia e satisfação.

**Histórias:** US06, US07, US02

**Justificativa:** Agrupa capabilities classificadas como Should Have que enriquecem a experiência mas não são críticas para MVP. US06 apoia postagem física (US04), US07 reduz fricções de suporte e US02 fecha o ciclo de gestão de conta. Este incremento pode ser executado em paralelo com INC03 ou postergado conforme restrições de time-to-market.

**Drivers Arquiteturais:**

- Geolocalização e busca espacial: integração com serviços de mapas, cálculo de proximidade e indexação geoespacial de agências
- Gestão de conteúdo de agências: sincronização de catálogo de pontos de atendimento (endereços, horários, serviços) com suporte offline
- Sistema de ticketing: integração com ServiceNow ou plataforma equivalente para gestão de solicitações de suporte via formulário
- Auditoria de alterações de perfil: rastreabilidade de mudanças em dados pessoais e consentimento para compliance LGPD/GDPR
- Cache geográfico: armazenamento local de agências previamente consultadas para funcionalidade offline de busca

---

## 9. Dependências entre Incrementos

### INC02 → INC01
INC02 (US03, US04) depende funcionalmente de INC01 (US01), pois compra de etiquetas requer autenticação e dados cadastrais do cliente. Sem conta criada, não há como processar transações ou associar etiquetas ao usuário.

### INC03 → INC02
INC03 (US05) possui dependência de dados com INC02 (US03), já que rastreamento opera sobre objetos postais originados da compra de etiquetas. Sem etiquetas emitidas, não há objetos a rastrear.

### INC04 → INC01
INC04 (US02) depende sequencialmente de INC01 (US01), pois edição de dados pressupõe existência prévia de conta. Adicionalmente, US06 e US07 podem se beneficiar de contexto autenticado para personalização, embora não sejam estritamente dependentes.

---

## 10. Riscos Técnicos

1. **Integração com Sistemas Legados:** Integração via CloudFoundry PaaS pode introduzir latências imprevisíveis, impactando especialmente INC02 (emissão de etiquetas) e INC03 (rastreamento) se APIs legadas forem síncronas e lentas.

2. **Arquitetura Offline-First:** Permeia todos os incrementos mas pode gerar complexidade exponencial se não for tratada desde INC01: sincronização, resolução de conflitos, versionamento de dados e gestão de filas de sincronização são desafios transversais.

3. **Conformidade Regulatória:** Conformidade simultânea com PCI-DSS (INC02 - pagamentos), LGPD/GDPR (INC01, INC04 - dados pessoais) e integração com SOC/ServiceNow (monitoramento) pode criar sobrecarga arquitetural e aumentar time-to-market se não houver patterns e bibliotecas corporativas estabelecidos.

4. **Dependência de APIs Externas:** Dependência de APIs externas de transportadoras (INC02) e rastreamento (INC03) introduz risco de disponibilidade e variabilidade de SLA fora do controle direto do time, exigindo estratégias robustas de circuit breaking e degradação graciosa.

5. **Segurança de QR Code:** Geração de QR Code offline (INC02 - US04) pode criar desafios de segurança se códigos puderem ser replicados ou reutilizados fraudulentamente, exigindo mecanismos de validação one-time-use ou time-bound tokens.

6. **Autenticação Incompleta:** A ausência de US relacionadas a recuperação de senha, reset de conta ou gestão de sessões em INC01 pode gerar débito técnico se o modelo de autenticação não for suficientemente robusto para suportar esses fluxos posteriormente.

7. **Rastreamento em Tempo Real:** Sincronização de status de rastreamento (INC03) em tempo real pode ser inviável se APIs de transportadoras operarem em batch ou com polling de baixa frequência, gerando expectativas não atendidas de 'tempo real'.

8. **Infraestrutura de Push:** A arquitetura de notificações push (INC03) requer infraestrutura adicional (APNS, FCM) que pode não estar provisionada, atrasando entrega de valor se considerada crítica.

9. **Compatibilidade Multiplataforma:** Compatibilidade Android/iOS impõe duplicação de esforços e potencial divergência de comportamento, especialmente para features offline e armazenamento local, aumentando custo de manutenção.

---

## 11. Observações sobre Prontidão

### 11.1 Arquitetura e Design

- A definição da arquitetura deve priorizar estratégia de sincronização offline antes de INC01, pois decisões sobre event sourcing, CQRS, eventual consistency ou outros patterns impactam todos os incrementos subsequentes
- É crítico estabelecer contratos de API (OpenAPI/Swagger) para integrações com transportadoras, Correios e sistemas legados antes de INC02, permitindo desenvolvimento paralelo via mocks/stubs
- A escolha do mecanismo de autenticação (OAuth2, JWT, session-based) em INC01 deve considerar cenários offline, renovação de tokens expirados e segurança em dispositivos móveis potencialmente comprometidos
- Padrões de criptografia para dados em repouso (INC01, INC02) devem ser definidos antecipadamente, considerando keychain iOS, keystore Android e rotação de chaves para compliance PCI-DSS/LGPD

### 11.2 Integração e APIs

- A estratégia de versionamento de APIs e backward compatibility deve ser estabelecida antes de INC02, considerando que aplicativos móveis não podem ser forçosamente atualizados instantaneamente
- Decisões sobre persistência local (SQLite, Realm, Core Data, shared preferences) impactam todos os incrementos e devem balancear performance, segurança, suporte offline e facilidade de sincronização
- A arquitetura de processamento de pagamentos (INC02) deve isolar lógica PCI-DSS em componentes específicos, minimizando scope de auditoria e facilitando certificação

### 11.3 Observabilidade e Operações

- Observabilidade (CloudWatch, AppDynamics, Datadog) e integração com SOC devem ser injetadas desde INC01 para acumular métricas de comportamento real antes de incrementos mais complexos
- A definição de RTO/RPO para disaster recovery deve considerar criticidade de cada incremento: INC02 (transações financeiras) provavelmente exige RTO/RPO mais agressivos que INC04

### 11.4 Qualidade e Experiência

- Testes de acessibilidade WCAG 2.1 e ABNT NBR 17060 devem começar em INC01 para estabelecer padrões de UI/UX que serão replicados em incrementos posteriores, evitando retrabalho
- A estratégia de feature flags/toggles deve ser considerada para permitir entrega de INC04 em paralelo com INC03 sem bloquear releases, especialmente se priorização mudar dinamicamente
- A arquitetura de localização (INC04 - US06) deve avaliar trade-offs entre precisão, consumo de bateria e privacidade, estabelecendo políticas de permissões que não comprometam conversão no onboarding

### 11.5 Parcerias e Contratos

- Contratos com transportadoras devem ser revisados antes de INC02 para validar disponibilidade de APIs, SLAs, custos de chamadas e políticas de rate limiting que podem impactar arquitetura de integração
- O modelo de dados de rastreamento (INC03) deve ser extensível para acomodar diferentes granularidades de eventos entre transportadoras (algumas reportam apenas checkpoints principais, outras fornecem telemetria detalhada)

### 11.6 Manutenibilidade

- A estratégia de migração de dados entre versões do aplicativo deve ser definida antes de releases subsequentes, considerando que clientes offline podem ter versões desatualizadas do schema local por períodos prolongados

---

## 12. Feedback de Planejamento

### 12.1 Riscos do Planejamento

- A integração com sistemas legados é ponto crítico e pode inviabilizar funcionalidades de rastreamento e status de objetos
- Falta de conectividade pode atrasar atualização de informações críticas (agências, rastreamento) em cenário offline
- Mudança futura nas regras de privacidade pode impactar o onboarding e captura de dados iniciais do usuário

### 12.2 Questões em Aberto

- Qual o fluxo e requisito para exclusão de conta e eventual retenção dos dados do usuário?
- Quais atributos mínimos devem constar nas agências para entrega de valor ao cliente (ex.: acessibilidade, serviços)?
- O canal de suporte via formulário está conectado a algum sistema de gestão de tickets ou é um contato simples?

### 12.3 Observações Gerais

- A granularidade das stories está adequada para planejamento e detalhamento incremental
- É recomendado detalhar políticas de atualização offline de dados críticos (rastreio, agências) ao refinar as stories
- Sincronização efetiva de dados de preferência de marketing e privacidade pode exigir análise adicional futura

---

## Controle de Versão

| Versão | Data | Autor | Mudanças |
|--------|------|-------|----------|
| 1.0 | 05/02/2026 | Claudecir Miranda | Versão inicial |

---

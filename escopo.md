1. Escopo de Funcionalidades do MVP/V1

O fornecedor deve colaborar com a Post Office para definir o escopo base do lançamento inicial, contemplando:

• **Conta do Cliente:** Criação e gestão de conta capturando nome, endereço, e-mail, celular e preferências de marketing.

• **Jornada de Compra Multitransportadora:** Compra de etiquetas de postagem com entrega em agência e **geração de QR Code** para postagem no balcão.

• **Rastreamento de Objetos:** Capacidade de rastrear encomendas compradas via aplicativo.

• **Localizador de Agências:** Busca de agências e exibição de informações detalhadas.

• **Ajuda e Suporte:** Canal de contato com a POL via formulários ou detalhes de contato integrados.

• **Compatibilidade e Padrões:** O app deve ser compatível com **Android e iOS**, atender aos requisitos de acessibilidade **WCAG** e possuir suporte ao **funcionamento offline**.

2. Experiência do Usuário (UX) e Design

O fornecedor é responsável por fornecer serviços de _insight_ e pesquisa, além de produzir:

• **Artefatos de Design:** Wireframes, protótipos e sistemas de design (_design systems_).

• **Fluxos de Processo:** Mapeamento de jornadas do usuário, navegação e integrações de serviço.

3. Arquitetura, Tecnologia e Consultoria Técnica

A solução deve ser integrada à infraestrutura da POL e ambientes de nuvem **AWS**, seguindo estas diretrizes:

• **Documentação Arquitetural:** Entrega de documentos HLD (_High Level Design_), LLD (_Low Level Design_), especificações de interface e planos de recuperação de desastres (RTO/RPO).

• **Segurança e Monitoramento:** Integração com o **SOC (Security Operations Center)** da Post Office e sistemas **ServiceNow** para alertas operacionais e de segurança.

• **Plataformas Adicionais:** Uso de **CloudFoundry PaaS**.

• **Capacidades de Consultoria:** O fornecedor deve prover expertise em arquitetura de microserviços, conformidade **PCIDSS**, segurança corporativa, IA, robótica e automação.

4. Ferramental (Tooling) e Entrega Ágil

A stack de ferramentas padrão da Post Office deve ser utilizada:

• **DevOps e CI/CD:** AWS Code Artifacts e **GitHub Actions**.

• **Observabilidade:** CloudWatch, **App Dynamics**, **Datadog** e **Wiz** (segurança).

• **Metodologia:** Entrega via **Scrum**, com gestão de backlog no **Jira**, histórias de usuário em formato **Gherkin** e rastreabilidade total de requisitos.

• **Testes:** Estratégia abrangente incluindo testes unitários, integração, UAT, End-to-End (E2E) e suporte a testes de intrusão (**PEN testing**) externos.

5. Governança e Transição para Operação (BAU)

O projeto exige uma estrutura de governança rigorosa para garantir a continuidade:

• **Estruturas de Governança:** Participação em _SteerCos_, fóruns de design técnico e conselhos de aprovação de _releases_.

• **Transição de Serviço:** Criação de um plano de transição para o modelo **BAU (****Business as Usual****)**, incluindo modelo RACI, treinamento de usuários e execução de cenários **"Game Day"** para transferência de conhecimento.

6. Experiência Relevante Exigida do Fornecedor

O fornecedor deve demonstrar histórico em:

• Desenvolvimento de estratégias de produto de ponta a ponta e identificação de "ganhos rápidos" para MVPs.

• Conhecimento profundo do setor de correspondências (_Mails_) e produtos específicos como o **Post Office Drop & Go**.

• Capacidade de alternar subcontratados/fornecedores caso metas e prazos estejam em risco.

• Experiência comprovada em suporte pós-lançamento e melhorias contínuas.

--------------------------------------------------------------------------------

Este estruturado consolida as exigências do apêndice, conectando as necessidades de negócio da Post Office com os padrões técnicos e operacionais esperados para o sucesso do aplicativo

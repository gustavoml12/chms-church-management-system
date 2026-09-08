# ChMS - Church Management System | PRODUTO (Documento de Negocio)

> Repositorio-raiz da descoberta de negocio validada na pagina de executacao entre Agente de Discovery e stakeholder NDS.
> Projeto Plane: `c4524fe2-fcd3-43aa-b7f3-88f86b51d3e4` (CHMS)

## 0. Contexto Executivo

Plataforma integrada **Web responsivo + PWA** para gestao eclesiastica, pastoral, financeira e de comunicacao de **igrejas protestantes independentes de 50-500 membros**. Substitui planilhas fragmentadas e processos manuais por um ecossistema seguro, centralizado e intuitivo para **voluntarios leigos**.

**Ancora estrategica (reason-to-buy): CRM pastoral / acompanhamento com foco em retencao de pessoas.** Finance serve de sustentacao economica.

## 1. Carta Magna & Posicionamento (Geoffrey Moore)

- **Para** pastores, tesoureiros, secretarios e lideres de igrejas protestantes independentes de 50-500 membros,
- **Que** sofrem de perda silenciosa de membros por falta de acompanhamento estruturado e de retrabalho/governanca fragil no fechamento e conciliacao financeira OFX,
- **O ChMS** e um **CRM pastoral + suite de gestao eclesiastica centrada em pessoas e retencao**, com financas de sustentacao,
- **Que** garante que ninguem caia no esquecimento: cada visitante/novo convertido recebe voluntario **titular + cover** do Ministerio de Boas-Vindas e plano de integracao a um ministerio, enquanto a tesouraria fecha o caixa em minutos com conciliacao OFX,
- **Diferente de** planilhas + WhatsApp + players 'enlatados' (ChurchTrac, Planning Center, Eklesia) que entram pela complexidade contabil e desmotivam o voluntario leigo,
- **Nosso produto** nasce blindado pela **simplicidade para o voluntario + modelo proprietario titular/cover de retencao** (moat) e conformidade LGPD de dados sensiveis.

## 2. Indicadores, KPIs & North Star

**North Star Metric:** Taxa de Retencao Trimestral de Membros Ativos - meta inicial **>= 97%** (evasao <= 3%), validavel/recalibravel com dados da 1a igreja-piloto. Leitura semanal pelo pastor.

| Camada | Metrica | Meta |
|---|---|---|
| North Star | Retencao trimestral | >= 97% (validavel) |
| Eficiencia | Fechamento de caixa | < 30 min (de 4-6h) |
| Eficiencia | 1o follow-up a novos | < 48h |
| Salus financiera | Conciliacao OFX | auto, divergencia explicada |
| ROI | Escandalo evitado + contrib. recorrente | renovacao mensal sustentada |

## 3. Matriz de Atores (resumo)

1. **Tesoureiro/Admin** - retrabalho de conferencia; conciliacao OFX manual terrivel; governanca dos gastos.
2. **Ministerio de Boas-Vindas (voluntarios)** - titular + cover, balanceamento de cotas, direcionamento a ministerio.
3. **Lider de Celula** - check-in colaborativo/automatico; oferta consolidada pelo tesoureiro.
4. **Secretario(a)** - cadastro central, historico ministerial, emissao rapida de certidoes.
5. **Pastor** - painel consolidado retencao/risco/financeiro.
6. **Membro/Visitante** - PWA carteirinha digital, agenda, oracao, presenca.

## 4. Jornada de Valor (Fluxo Novo Convertido + Integracao)

(Ver diagrama Mermaid SVG na Page 04 do Plane CHMS (145498a5) e nesta issue via imagem embutida).

Etapas: Entrada/cadastro -> Acionamento Boas-Vindas (balanceamento) -> Atribuicao titular+cover -> Acompanhamento (check-in + checkpoints) -> Risco/convergencia (alerta MIR 48h OU avanco) -> Integracao a ministerio -> Retencao (North Star) em loop continuo.

## 5. Regras de Negocio Invariantes (RN-01..05)

- **RN-01 Titular + Cover Obrigatorio**: nada sem par completo; cover promovido a titular quando necessario.
- **RN-02 LGPD Sensiveis**: consentimento explicito + trilha de auditoria de acesso + direito ao esquecimento em ate 15 dias.
- **RN-03 Elegibilidade / Membro em Risco**: ausente 14d -> MIR; nao marcavel 'presente' sem registro de contato.
- **RN-04 Integridade Financeira OFX**: conciliacao continua (pendente marcado, sem travar balancete) + gatilho de divergencia com alerta ao pastor e justificativa registrada.
- **RN-05 Ciclo de Vida**: ativo com >=1 atividade/30d; Desligado/Nao-membro apos 60d sem atividade e sem contato; fluxo de reingresso.

## 6. Escopo da 1a entrega & Anti-Escopo

**ENTRA (nucleo):** Membresia/CRM pastoral; Ministerio de Boas-Vindas; financas de sustentacao + conciliacao OFX; presenca/celula + risco de retencao; PWA membro; comunicacao WhatsApp; painel do pastor; Web secretaria/tesouraria; RBAC; LGPD-by-design.

**FORA (evolucao continua):** portal de doacoes online com gateway; app nativo completo (usa-se PWA); multi-denominacao/estrutura matriz+filiais; gestao de patrimonio + governanca documental avancada. Publicacao associada a membresia permanece auditoria leve (nao regra de negocio).

## 7. Release Plan & Estimativa (agente, ajustada)

**~14 sprints quinzenais (~7 meses)** com time menor/junior + onboarding; 7 fases (modulos): Fase 0 Fundacao; Fase 1 Membresia; Fase 2 Boas-Vindas; Fase 3 Presenca/Risco (BETA); Fase 4 Financas OFX; Fase 5 PWA+WhatsApp; Fase 6 Painel Pastor/QA/Release. Datas: 2026-09-15 a 2027-01-19.

## 8. Visao de produto vivo

Itens fora do corte entram por novas rodadas formais e negociadas de escopo; incrementos regidos pelas regras ate formalmente alteradas.

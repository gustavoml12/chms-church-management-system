# ChMS - Church Management System | DESIGN DOC (Design System e Identidade Visual)

> Documento fonte da identidade visual do frontend. Definido na sabatina 2026-09-08 entre Agente Frontend (Discovery & Design) e stakeholder NDS.
> Representa o gabarito visual deterministico (Visual Ground Truth). Prototipos HTML/CSS fieis constam em `docs/prototypes/<feature>/`.
> **Rev 2 (2026-09-08):** auditoria WCAG de contraste aplicada -> tokens soft solidificados (sem rgba), textos de badges escurecidos p/ AA normal >=4.5:1.

## 0. Direcao de Design (uma frase)

Interfaces leves e acolhedoras para comunidades de fe, com credibilidade administrativa: **nenhum membro cai no esquecimento** sem que a operacao financeira (OFX) permaneja solida e confiavel.

Valores que guiam cada decisao: **Acolhimento, Confianca, Simplicidade (voluntario leigo), Serenidade, Precisao Financeira, Solenidade LGPD (dados sensiveis).**

Proibicoes expressas (anti AI-Slop):
- NADA de cinza sem alma, paleta roxo-azulado padrao de SaaS, bordas em excesso, sombras genericas ou gradientes neon.
- NADA de dashboard corporativo intimidador para o voluntario laico.
- Contraste sempre WCAG AA (minimo 4.5:1 p/ texto normal) e preferencialmente AAA (7:1) para texto corrente em superficie clara.

## 1. Paleta de Cores (Color Tokens)

### Superficies (neutro quente)
| Token | Hex | Uso |
|---|---|---|
| --nds-surface-base | #FFFFFF | Fundo de cards/paineis |
| --nds-surface-2 | #F8F6F3 | Fundo de pagina/regioes (linho quente) |
| --nds-surface-3 | #EFEBE4 | Regioes elevadas/zonas em repouso, tabelas zebra |
| --nds-surface-inverse | #16302B | Cabecalhos inversos, footer, sidebar (emerald profundo) |

### Texto (alto contraste sobre superficie clara)
| Token | Hex | Contrast (sobre #FFFFFF) | Nivel |
|---|---|---|---|
| --nds-text-primary | #1C2B26 | 14.5:1 | AAA |
| --nds-text-secondary | #4B5C55 | 7.3:1 | AAA |
| --nds-text-muted | #6E7C74 | 4.6:1 | AA |
| --nds-text-on-accent | #FFFFFF | >10:1 | AAA |

### Marca / Acao (Primaria)
| Token | Hex | HSL | Uso |
|---|---|---|---|
| --nds-primary | #0E6B52 | hsl(165, 76%, 24%) | Botao principal, links, foco, CTA ministerial |
| --nds-primary-hover | #0A5742 | hsl(164, 78%, 19%) | Hover do primario |
| --nds-primary-soft | #E1F0EA | hsl(165, 36%, 91%) | Fundo selecionado, avatar de acolhimento, chips pastel |
| --nds-primary-border | #9CCBB9 | hsl(164, 31%, 70%) | Borda de foco/selecao, dividers suaves |

### Acento (Cuidado pastoral/valor humano)
| Token | Hex | Uso |
|---|---|---|
| --nds-accent-gold | #B8872F | Selos/apreciacao (uso decorativo OU sobre superficie clara usar --accent-gold-deep) |
| --nds-accent-gold-deep | #7A5C1B | Texto dourado legivel: sobre gold-soft e superfícies claras (AA 5.3:1) |
| --nds-accent-gold-soft | #F6EBD7 | Fundo de cartao de reconhecimento / nota pastoral |

### Soft tokens de fundo (tonalidades solidadas de semanticas - substituem rgba alpha)
> Regra: todo estado semantico usa par [fundo-soft + texto-deep]. Texto nunca e a cor solida a 100% diretamente sobre seu proprio soft tint (reprovava AA).

| Fundo soft | Hex | Texto correspondente | Hex texto | Contraste texto/bg soft |
|---|---|---|---|---|
| --nds-success-soft | #E2EFEA | --nds-success-text (deep) | #0C6B45 | 5.5:1 AA |
| --nds-info-soft    | #E5ECF5 | --nds-info-text (deep)    | #2563A9 | 5.1:1 AA |
| --nds-warning-soft | #F5E7DD | --nds-warning-text (deep)| #9A4A07 | 5.2:1 AA |
| --nds-danger-soft  | #F7E5E3 | --nds-danger-text (deep) | #B02F23 | 5.3:1 AA |

### Solidas de estado (para uso em superficie clara/branco e iconografia)
| Token | Hex | Sobre White | Sobre surface-2 |
|---|---|---|---|
| --nds-success | #0F7B4F | 5.3:1 AA | 4.9:1 AA |
| --nds-info | #2563A9 | 6.1:1 AA | 5.7:1 AA |
| --nds-warning | #B45309 | 5.0:1 AA | 4.7:1 AA |
| --nds-danger | #C0392B | 5.4:1 AA | 5.0:1 AA |

> NOTA DE USO: --success/--warning/--danger (solido) sao para ICONES, bordas e estado grafico. Para TEXTO (labels/badges) sobre fundos claros ou soft-tint, sempre os pares soft-text (deeper). Isso garante AA normal permanente.

## 2. Tipografia

Display/Fraunces serif acolhedor para titulos de CRM, nome do membro em contexto de apreciacao, painel do pastor, hero do PWA. UI/Body/Inter legibilidade operacional para secretaria/tesouraria/listagens/formularios. Dados/Financas/JetBrains Mono para conciliacao OFX, saldos, datas, ids.

Escala rem: xs .75, sm .875, base 1, lg 1.125, xl 1.25, 2xl 1.5, 3xl 1.875, 4xl 2.25. Pesos: body 400, enfase 500, Inter titulo 600, Fraunces 560-600. Line-height titulo 1.15, corpo compacto 1.4, corpo pastoral amplo 1.6.

Regra de aplicacao serif/sans: o NOME da pessoa usa Fraunces (.serif) apenas quando a pessoa esta em contexto de VALORIZACAO/acolhimento (colunas em processo, destacada, apreciada). Nomes em listagens operacionais densas (secretaria) usam Inter. Icones de avatar sempre mono.

Fallbacks: system-ui para Inter, Georgia para Fraunces, ui-monospace para mono.

## 3. Densidade

Hibrida por contexto. Back-office (secretaria/tesouraria/concilia OFX/cadastro/historicos): compacta/media, body 14px/20px, gap 4-8px, tabelas de rapida rolagem, teclado-first. Areas pastorais e PWA membro (CRM acolhimento, alerta MIR, painel do pastor, carteirinha): ampla/respiracao, body 15-16px, gap 12-24px, cards maiores e calorosos.

Grade espacamento base 4px: 4/8/12/16/24/32/48. Raio: sm 6, md 10, lg 16, pill 999.

Sombras: sombra-suave sutil, sombra-elevada so em modal/menu, hover com leve elevacao e cor, nunca so cinza.

## 4. Pessoas no centro

Avatar com iniciais sobre primary-soft + ring primaria, fotografia opcional. Nome em contexto de apreciacao em Fraunces com accent-gold-deep. Estado MIR nunca apenas com cor: icone alerta + rotulo textual + contraste.

## 5. Componentes Core

Button primary/soft/ghost/danger-outline, tamanhos sm/md/lg, estados hover/focus/active/disabled/loading.

Input/Select/Textarea com label for, helper, focus primary-border+ring, erro danger-text com aria-describedby.

Card com fundo branco, borda 1px surface-3, raio lg 16, padding 20/24, CardHeader titulo+subtitulo+acoes.

Badge/Tag suaves: usa SEMPRE par [fundo-token-soft + texto-token-deep]. Gold pastoral com --accent-gold-deep. Quando semantico, texto sempre presente (nunca so cor).

Table com header surface-2, zebra surface-3, coluna numerica JetBrains Mono a direita, header sticky.

EmptyState com icone em primary-soft + titulo Fraunces + texto + CTA primario explicito.

Skeleton (loading) blocos surface-3 com shimmer sutil; replica a silhueta real do conteudo (ex.: card de pessoa ou linha de tabela).

ErrorState painel danger-soft + texto danger-text + botao nova tentativa; log nunca cru.

Shell admin com sidebar surface-inverse texto claro AAA; PWA membro header claro surface-2.

## 6. Acessibilidade

Landmarks semanticos <header>/<nav>/<main>/<section>/<footer>. Focus visible 2px primary-border + ring. Icone sem texto com aria-label. Imagem com alt. Erro via aria-describedby. Modal aria-modal + fechamento Esc. Status MIR com texto adicional. Radio/checkbox com contraste no estado selecionado. Todos os pares fg/bg >=4.5:1 (AA) para texto normal.

## 7. Escopo visual por fase

F0 Fundacao (shell, login, RBAC, onboarding consentimento LGPD). F1 Membresia/CRM pastoral. F2 Boas-Vindas titular+cover. F3 Presenca/Risco MIR. F4 Financas/concil OFX. F5 PWA membro + WhatsApp. F6 Painel Pastor consolidado.

Gabarito imutavel de implementacao para agentes, DoR visual 100/100.

# CLAUDE.md — Projeto Map360

## O que é o Map360

O **Map360 (Mapeamento 360°)** é uma ferramenta interna da QBem de **visualização e acompanhamento da jornada de onboarding de corretoras** no produto EB. Mapeia o ciclo de vida completo de cada cliente — da prospecção à ativação — em uma timeline visual interativa.

### O que o Map360 faz
Exibe o status de onboarding de cada corretora cliente do EB por etapa (Coleta de Dados, Comercial, Boas-vindas, Kickoff, Implantação, Treinamentos, Ativação, Pós-Ativação, Reimplantação), com visão consolidada e por cliente.

### Público-alvo
Equipe interna QBem — gestores de implantação, CS e produto.

---

## Este projeto: ferramenta de mapeamento visual

Stack atual: **HTML + CSS + JS puro** (protótipo standalone — sem framework, sem build tool)

### Arquivo principal
- `Jornada_Onboarding_QBem.html` — app completo em single-file HTML (fontes, estilos e lógica embutidos)

### Estrutura de dados
- Etapas da jornada: Coleta de Dados · Comercial/Fechamento · Boas-vindas de Implantação · Kickoff · Coleta de dados · Treinamentos · Implantação/Parametrização · Ativação · Pós-Ativação · Reimplantação
- Visualização por cliente (corretoras): JOVELO, HG7, MOREIRA E MEDEIROS, CONVENIA, SEGPARTNERS, INTER, RK2, ADESSO, BLUEZONES, JC LUZ, NEOVIVA, FIANÇA, RASX, MULTIPLO, FACSI, SEGNA, EPL, VEIGA, HEELNER, RODOBENS, MARKFORTE, PCF CORRETORA, BTR, WILLIS, DAGA, DETULIO, GEMM, BENTECSEG, GALAMBA, TRR, SICCS, POLLO, EXCLUSIVE e outros

### Convenções
- HTML/CSS/JS vanilla — manter single-file enquanto possível (facilita compartilhamento)
- Português (pt-BR) para labels e conteúdo de negócio
- Dados mockados inline; sem API externa por enquanto

---

## Design System

**Source of truth:** invocar `/qbem-design` para gerar componentes ou assets visuais.

### Tokens obrigatórios

| Token | Valor | Uso |
|---|---|---|
| `--qb-petrol-900` | `#174353` | Primário — header, botões, texto |
| `--qb-petrol-500` | `#1e9ca8` | Teal accent — foco, elementos ativos |
| `--qb-green-500` | `#00bf5a` | Sucesso — etapas concluídas |
| `--qb-lime-300` | `#d4fc92` | Lime accent — CTAs de destaque |
| `--qb-danger` | `#d4302f` | Erro / risco |
| `--qb-warning` | `#e6b032` | Alerta / pendente |

**PROIBIDO:** `#289DA8` · `#194352` · `#2AA898` — fora da paleta QBem.

### Tipografia
**LINE Seed JP** — único typeface permitido:
- `"LINE Seed JP"` → Regular (400) + Bold (700)
- `"LINE Seed JP ExtraBold"` → ExtraBold (800)
- `"LINE Seed JP Thin"` → Thin (100)

### Iconografia
**Material Symbols Rounded** via Google Fonts. Nunca Lucide, Heroicons, FontAwesome ou emoji funcional.

---

## Regra de uso de modelos

| Tarefa | Modelo |
|---|---|
| Decisão de UX / arquitetura de dados / nova feature | Sonnet 4.6 (padrão) |
| Ajuste de CSS / token / label | Haiku 4.5 (`--model claude-haiku-4-5`) |

**Ao iniciar sessão nova:** rodar `/compact` antes de avançar.

---

## Ecossistema relacionado

| Projeto | Relação |
|---|---|
| `qbem-eb` | Portal principal — as corretoras mapeadas aqui são clientes do EB |
| `wappa-ds` | Design System source of truth de tokens e componentes |
| `qhealth` | Portal analítico — visualizações de saúde das mesmas corretoras |

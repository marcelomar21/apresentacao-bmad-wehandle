# Meetup Cmapinas Q1 - Roteiro Completo

---

## Slide 1: O que é BMAD?

**BMAD** = Breakthrough Method for Agile AI-Driven Development

### Resumo:
Framework open-source que transforma desenvolvimento com IA de "vibe coding" (fazer código sem plano) em workflows estruturados e production-ready.

### Detalhes:
- **43k stars** no GitHub (top 50 repositórios)
- **V6** lançado em 2026 com Module Ecosystem
- **12+ agentes especializados**: PM, Architect, Developer, UX, Scrum Master, QA, Technical Writer
- **34+ workflows** estruturados
- **Scale-adaptive**: ajusta profundidade conforme complexidade do projeto
- Criado pela comunidade, 100% free

### Por que surgiu?
> "I just see things, say things, run things, and copy-paste things, and it mostly works."
> — Andrej Karpathy, Feb 2025

BMAD resolve o problema de IA que funciona em demos mas falha em produção.

---

## Slide 2: Frameworks Similares

### Comparativo:

| Framework | Criador | Tipo | Diferencial |
|-----------|---------|------|-------------|
| **BMAD** | Comunidade | Metodologia + Agentes | Workflow completo, 12+ agentes |
| **Spec Kit** | GitHub | Specification-driven | SPEC.md como fonte de verdade |
| **Claude Code** | Anthropic | AI CLI | Execução autônoma de tarefas |
| **AgentOS** | Various | Sistema operacional | Orquestração multi-agente |
| **Cursor** | Anysphere | IDE + AI | Editor com AI integrado |

### Por que escolher BMAD?
- **Scale-adaptive**: Bug fix = workflow leve; Enterprise = workflow completo
- **Metodologia + Tooling**: Não é só ferramenta, é processo
- **Comunidade ativa**: 131 contribuidores, 28 releases

---

## Slide 3: Por que Guardrails são necessários?

### O Problema Real:

1. **IA funciona em demos, falha em produção**
   - Código gerado parece bom mas não escala
   - Falta testes, documentação, edge cases

2. **Casos de falha costly**
   - Exemplo: 847 retries = $2,200 em custos de API
   - Agente enviou 14 emails parcials para 1 cliente

3. **Falta de estrutura = código espaguete**
   - Sem padrões = código inconsistente
   - Dificuldade de manutenção

4. **Sem accountability**
   - Quem é responsável pelo código?
   - Como auditar decisões?

### A Solução: Guardrails
Barreiras arquiteturais que:
- Guidam a IA em cada fase
- Estabelecem padrões de código
- Validam outputs automaticamente
- Criam traceability

---

## Slide 4: Harness Engineering

### Definição:
> "A disciplina que faz agentes IA serem confiáveis em produção"

### O que NÃO é:
- ❌ Prompt engineering com outro nome
- ❌ Mais prompts = melhor IA
- ❌ Solução mágica

### O que É:
- ✅ Arquitetura de guardrails (padrões de execução)
- ✅ Infraestrutura de controle (retry, timeout, circuit breaker)
- ✅ Métricas e observabilidade (o que está rodando?)
- ✅ Padrões de segurança (rate limiting, sanitização)
- ✅ Workflows estruturados

### Por que importa?
> "Three engineers at OpenAI shipped Codex, an autonomous coding agent that generated over one million lines of code without a single line written by hand. The model behind it was impressive. But the model was not the secret."
> — Kai Renner, Harness Engineering

O segredo era a **arquitetura ao redor do modelo**, não o modelo em si.

---

## Slide 5: Os 8 Níveis de Agentic Engineering

*[Imagem: The 8 Levels of Agentic Engineering.jpeg]*

| Nível | Nome | Descrição |
|-------|------|-----------|
| 1 | **Simple Task** | One-shot prompts, sem estado |
| 2 | **Sequential** | Multi-step, mas sem memória |
| 3 | **With Memory** | Contexto persiste entre chamadas |
| 4 | **With Tools** | Acessa APIs, sistema de arquivos |
| 5 | **Planning** | Think before act (reflection) |
| 6 | **Multi-Agent** | Múltiplos agentes colaboram |
| 7 | **Evaluative** | Auto-avaliação e correção |
| 8 | **Autonomous** | Self-improving, production-ready |

### BMAD posiciona onde?
- BMAD leva projetos do **Nível 3 → Nível 8**
- Workflows estruturados = avaliação contínua
- Multi-agent = 12+ agentes especializados

---

## Slide 6: Ciclo de Desenvolvimento com BMAD

### Create PRD (Product Requirements Document)

**Antes (Humano):**
- PM conduzia reunião de 1-2h
- Documento em Word/Google Docs
- Revisão manual por stakeholders
- Tempo: 1-2 dias

**Com BMAD:**
- Input: ideia/note rápida
- Output: PRD estruturado em markdown
- Validação automática de completude
- Tempo: minutos

**Fluxo BMAD:**
```
Ideia → Geração PRD → Validação → Revisão humana → Final
```

---

### Quick Spec

**Antes (Humano):**
- Architect revisava requisitos
- Criava spec técnica em Confluence/Notion
- Aprovação por email/reunião
- Tempo: 1 dia

**Com BMAD:**
- Input: PRD + contexto
- Output: SPEC.md completo
- Inclui: Tech stack, API design, DB schema
- Tempo: minutos

**Fluxo BMAD:**
```
PRD → Análise técnica → Geração SPEC → Validação → Aprovação
```

---

### Create Epics

**Antes (Humano):**
- PO quebrava features em épicos
- Planning session semanal
- Jira epics → stories → tasks
- Tempo: sessão de 2-4h

**Com BMAD:**
- Input: SPEC.md
- Output: Epics estruturados
- Com:escopo, dependências, priorities
- Tempo: automático

**Fluxo BMAD:**
```
SPEC → Decomposição → Epics → Categorização → Priorização
```

---

### Create Stories

**Antes (Humano):**
- Developer quebrava em tasks
- Estimava story points
- Criava sub-tasks no Jira
- Cada story: ~30min

**Com BMAD:**
- Input: Epics
- Output: User stories com:
  - Título
  - Descrição (Given/When/Then)
  - Critérios de aceite
  - Tasks técnicas
- Tempo: minutos para todas

**Fluxo BMAD:**
```
Epic → Stories → Tasks → Critérios → Estimativas
```

---

### Code Review

**Antes (Humano):**
- Developer abria PR
- Revisor analisava código (30min-1h)
- Comments no GitHub
- Iterações de "fix this"

**Com BMAD:**
- BMAD gera código
- Code review prévio automático:
  - Padrões de código
  - Security scan
  - Test coverage
  - Doc generation
- Revisor humano foca em lógica de negócio

**Fluxo BMAD:**
```
Código → Auto-review → Críticas → Correções → PR Ready
```

---

### Pull Request Final

**Antes (Humano):**
- Revisor aprovava (ou não)
- Merge manual
- Docs eram opcionais
- Tiempo: variável

**Com BMAD:**
- Validação final:
  - [ ] Tests passing
  - [ ] Docs updated
  - [ ] Security scan clean
  - [ ] Code coverage
- PR pronto com descrição completa
- Tempo: automático

**Fluxo BMAD:**
```
Code Review → Validações → Docs → Descrição PR → Ready to Merge
```

---

## Slide 7: Demonstração

### O que mostrar:
1. Pasta _bmad instalada
2. Executar: `npx bmad-help` ou `bmad-help`
3. Criar um PRD de exemplo
4. Mostrar Quick Spec gerado
5. Mostrar Epics e Stories

### Comandos:
```bash
cd meetup_cmapinas_q1
npx bmad-method install  # se necessário
bmad-help                #invoke skill
```

---

## Slide 8: Obrigado!

- **docs.bmad-method.org**
- **discord.gg/gk8jAdXWmj**
- **github.com/bmad-code-org/BMAD-METHOD**

Meetup Cmapinas - Q1 2026

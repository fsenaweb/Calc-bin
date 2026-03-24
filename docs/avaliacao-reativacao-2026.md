# Avaliação de Reativação do Projeto `calc-bin` (março/2026)

## 1) Estado atual (diagnóstico rápido)

- **Stack principal**: Vue 2.3 + Quasar Framework 0.14 + Webpack 3 + Babel 6.
- **Build local**: `npm run lint` e `npm run build` executam com sucesso no ambiente atual.
- **Sinais de obsolescência**:
  - Dependências muito antigas e fora do ciclo de manutenção.
  - Ferramentas de build legadas (`webpack 3`, `babel 6`, `eslint-loader`, `json-loader`).
  - README ainda orientado ao fluxo antigo com `quasar dev/build/lint`, enquanto os scripts reais do projeto usam `node build/script.*.js`.

## 2) Risco técnico para “reativar sem mexer”

É **possível subir o projeto no curto prazo** sem alteração estrutural, mas com risco alto de:

- Quebra em máquinas com versões recentes de Node/npm.
- Maior exposição a CVEs de dependências transientes antigas.
- Dificuldade de manutenção (onboarding e atualização de tooling).

Em resumo: **reativar do jeito atual é viável só como contingência temporária**.

## 3) Precisaremos de breaking change?

### Resposta curta

**Sim, muito provavelmente haverá breaking change** se a meta for reativação sustentável.

### Por quê

A atualização para ecossistema moderno (Vue 3 + Quasar atual + Vite) implica mudanças de:

- API de componentes e lifecycle.
- plugins e bootstrap.
- cadeia de build e lint.

Mesmo que a regra de negócio (conversão de bases) seja simples, a camada de framework/build terá mudanças incompatíveis.

## 4) Estratégia recomendada

### Opção A — “Sobrevida rápida” (sem breaking externo, curto prazo)

Objetivo: recolocar em produção rapidamente com mínima alteração funcional.

1. Congelar versão de Node via `.nvmrc` e documentar versão suportada.
2. Ajustar README para comandos reais (`npm run dev/build/lint`).
3. Executar auditoria de dependências e corrigir o que não quebrar API.
4. Publicar como versão de manutenção.

**Prós**: menor esforço imediato.  
**Contras**: dívida técnica permanece alta.

### Opção B — “Reativação correta” (com breaking controlado)

Objetivo: tornar o projeto mantível pelos próximos anos.

1. Criar branch/versão major (ex.: `v1 -> v2`).
2. Migrar gradualmente para stack moderna (Vue/Quasar atuais, build moderno).
3. Extrair e cobrir a lógica de conversão com testes unitários.
4. Validar comportamento com testes de regressão (entrada/saída de conversão).
5. Publicar guia de migração (breaking notes).

**Prós**: manutenção e segurança muito melhores.  
**Contras**: exige planejamento e janela de mudança.

## 5) Recomendação final

Se a intenção é **reativar para uso contínuo**, recomendo:

- Fazer uma entrega curta de estabilização (Opção A) para voltar a operar.
- Em paralelo, iniciar migração major (Opção B) já com cronograma.

Isso reduz risco operacional hoje sem perpetuar o legado indefinidamente.

## 6) Próximos passos práticos (1 a 2 semanas)

1. Definir versão alvo de Node e publicar no repositório.
2. Adicionar testes unitários para as conversões (bin/dec/hex/oct).
3. Corrigir documentação de execução local.
4. Levantar backlog de migração (framework, build, lint, CI).
5. Decidir data de corte para release major com breaking change.

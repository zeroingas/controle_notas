# Convenções deste projeto

## Versão do app

O cabeçalho de `index.html` (ZERO! Controle) mostra um número de versão pequeno,
alinhado à direita, embaixo do título (`<small class="app-version">v1.1.1</small>`).

**Sempre que alterar `index.html` de forma perceptível ao usuário** (interface,
comportamento, correção de bug visível), incrementar essa versão antes de
commitar:
- mudança pequena/patch (ajuste visual, correção de bug pontual): sobe o último número (1.1.1 → 1.1.2)
- funcionalidade nova: sobe o número do meio (1.1.x → 1.2.0)
- mudança grande/estrutural: sobe o primeiro número (1.x.x → 2.0.0)

## Service worker / cache

`sw.js` tem `CACHE_NAME = 'notas-app-vN'`. Sempre que qualquer arquivo do app
mudar, incrementar N — senão a atualização não chega nos aparelhos que já
instalaram o PWA (o service worker só troca o cache quando o nome muda).

Depois de publicar, lembrar o usuário de fechar o app completamente e abrir
de novo (às vezes duas vezes) pra pegar a atualização.

## Fluxo de entrega

Depois de validar a sintaxe do `<script>` (via `node -e` extraindo o bloco),
commitar, dar push pra `claude/e-agora-mccmsr`, abrir PR pra `main` e
mesclar automaticamente (sem precisar perguntar, conforme combinado com o usuário).

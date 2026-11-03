# Carta de plasticidade de Casagrande

Página web interativa para classificar a **fração fina de solos** (SUCS / ASTM D2487) a partir do limite de liquidez (LL) e do índice de plasticidade (IP) ou do limite de plasticidade (LP).

## Recursos

- Ponto plotado na carta em tempo real, com guias até os eixos
- Entrada por **LL e IP** ou por **LL e LP** (IP = LL − LP calculado automaticamente)
- Também é possível clicar ou arrastar no gráfico para posicionar o ponto
- Classificação: CL, CH, ML/OL, MH/OH e CL-ML, com descrição
- Linha A (IP = 0,73·(LL − 20)), linha U (IP = 0,9·(LL − 8)), LL = 30 e LL = 50
- Região de solos não coesivos (IP < 4)
- Avisos para IP > LL, LP > LL e pontos acima da linha U
- Exemplos prontos e seção de teoria com todas as siglas
- Tema claro e escuro automático

## Como usar

Não há dependências nem etapa de build. Abra o `index.html` no navegador.

Com o GitHub Pages ativado (veja abaixo), a página fica publicada em
`https://<seu-usuario>.github.io/<nome-do-repositorio>/`.

## Lógica de classificação

| Posição na carta | Símbolo |
|---|---|
| Acima da linha A, 4 ≤ IP ≤ 7 | CL-ML |
| Acima da linha A, IP ≥ 4, LL < 50 | CL |
| Acima da linha A, IP ≥ 4, LL ≥ 50 | CH |
| Acima da linha A, IP < 4 (não coesivo) | ML |
| Abaixo da linha A, LL < 50 | ML (ou OL) |
| Abaixo da linha A, LL ≥ 50 | MH (ou OH) |

A carta não separa solos inorgânicos de orgânicos. Para isso, use a razão entre o LL do solo seco em estufa e o LL natural (< 0,75 indica solo orgânico). A classificação completa pelo SUCS também exige a granulometria.

## Publicar no GitHub Pages

Em **Settings → Pages → Build and deployment**, escolha **GitHub Actions**. O workflow em `.github/workflows/pages.yml` publica a página a cada push na branch `main`.

## Fluxo de atualização

```bash
git add -A
git commit -m "feat: descrição da mudança"
git push
```

Sugestão de prefixos de commit: `feat`, `fix`, `docs`, `style`, `refactor`, `chore`.

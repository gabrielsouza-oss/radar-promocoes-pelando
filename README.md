# Radar de promoções do Pelando

Coleta ofertas recentes e comentadas do Pelando, calcula métricas de engajamento
e recência, e publica um painel HTML no GitHub Pages.

## Atualização automática

O workflow em `.github/workflows/pelando.yml` executa a coleta a cada 30 minutos
(cron em UTC), também após alterações na branch `main` e quando iniciado
manualmente pela aba **Actions**. O HTML gerado é publicado em:

<https://gabrielsouza-oss.github.io/radar-promocoes-pelando/>

Em **Settings → Pages**, a origem de publicação deve estar configurada como
**GitHub Actions**. O workflow usa `GITHUB_TOKEN` e não precisa de um token
pessoal.

## Execução local

```shell
python -m pip install -r requirements.txt
jupyter nbconvert --to notebook --execute pelando_promocoes.ipynb --output pelando_promocoes_executed.ipynb
```

O notebook gera `pelando_ofertas.html`. A publicação local opcional pede um
token GitHub interativamente.

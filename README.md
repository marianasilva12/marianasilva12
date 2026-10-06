name: Generate Snake

on:
  schedule:
    # executa a cada 6 horas
    - cron: "0 */6 * * *"
  
  # permite executar manualmente a action na aba Actions
  workflow_dispatch:
    
  # executa em cada push na branch main
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      
      - name: Generate Snake
        uses: Platane/snk/svg-only@v3
        id: snake-gif
        with:
          github_user_name: marianasilva12  # <--- Substitua pelo SEU nome de usuário
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      
      - name: Push to output branch
        uses: crazy-max/ghaction-upload-artifact@v3
        with:
          name: github-contribution-grid-snake-svg
          path: dist
          <p align="center">
  <video width="360" height="auto" controls autoplay loop muted>
    <source src="SEU-LINK-DO-VIDEO.mp4" type="video/mp4">
    Seu navegador não suporta a tag de vídeo.
  </video>
</p>

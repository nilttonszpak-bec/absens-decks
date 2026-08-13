# absens-decks

Apresentações HTML do Absens publicadas como páginas web pelo GitHub Pages.

**Site:** https://nilttonszpak-bec.github.io/absens-decks/

## Uso

A central e os links das apresentações são de **uso interno da equipe Beyond Co.**
Para compartilhar com cliente, baixe o **PDF** pelo botão do card e envie o arquivo.

O repositório é público: quem tem a URL abre a página. O `robots.txt` e a meta `noindex`
mantêm tudo fora dos buscadores, mas isso não é controle de acesso — nada sob sigilo
contratual deve ser publicado aqui.

## Estrutura

```
absens-decks/
├── index.html                          <- central que lista os decks
├── .assets.json                        <- manifesto de arquivos a publicar
├── .github/workflows/publicar-assets.yml
└── apresentacao-executiva/
    ├── index.html                      <- o deck (abre no navegador)
    └── absens-apresentacao-executiva.pdf
```

Cada apresentação é uma pasta com `index.html` dentro — é isso que faz a URL terminar
na pasta, sem `.html` à mostra.

## Publicar ou atualizar uma apresentação

Há dois caminhos. Ambos preservam o link já compartilhado.

**Pela interface do GitHub:** entre na pasta do deck, use *Add file → Upload files* e
suba o HTML renomeado para `index.html` (e o PDF, se houver). O site atualiza em cerca
de um minuto.

**Pelo manifesto:** edite o `.assets.json` apontando cada arquivo público para o destino
dentro do repositório. Ao salvar, o workflow baixa e commita os arquivos sozinho — útil
para arquivos grandes, que a API de conteúdo não aceita direto.

```json
[
  { "dest": "nome-do-deck/index.html", "url": "https://.../deck.html" }
]
```

Depois, adicione o card correspondente no `index.html` da raiz, com os três botões:
abrir, baixar PDF e baixar HTML.

## Regras

- **O link é permanente.** Substituir o `index.html` da pasta atualiza a apresentação sem
  trocar o endereço.
- **Não renomeie a pasta** depois de compartilhar: o nome da pasta é o link.
- **Um deck, um arquivo.** Os HTMLs são autocontidos (fonte, logo e imagens embutidos),
  então não há dependência externa para quebrar.
- Nomes de pasta em minúsculas, com hifens e sem acento.

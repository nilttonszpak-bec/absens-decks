# absens-decks

Apresentações HTML do Absens publicadas como páginas web pelo GitHub Pages.

**Site:** https://nilttonszpak-bec.github.io/absens-decks/

## Duas versões por apresentação

Cada deck existe em duas versões, e o card na central tem um seletor que troca as três ações
(abrir, baixar PDF, baixar HTML) entre elas:

| Versão | Para que serve | Onde fica |
|---|---|---|
| **Uso ao vivo** | Conduzir a apresentação. Slides interativos, ambientes simulados. | `<deck>/` |
| **Envio p/ cliente** | Compartilhar. Cada estado interativo virou um slide estático, então nada se perde no PDF nem para quem só avança os slides. | `<deck>/cliente/` |

O PDF da versão de envio é o que vai para o cliente. O da versão ao vivo existe para referência
interna e, por natureza, mostra só um estado de cada tela interativa.

## Uso

A central e os links são de **uso interno da equipe Beyond Co.** O repositório é público: quem
tem a URL abre a página. O `robots.txt` e a meta `noindex` mantêm tudo fora dos buscadores, mas
isso não é controle de acesso — nada sob sigilo contratual deve ser publicado aqui.

## Estrutura

```
absens-decks/
├── index.html                          <- central que lista os decks
├── .assets.json                        <- manifesto de arquivos a publicar
├── .github/workflows/publicar-assets.yml
├── apresentacao-executiva/
│   ├── index.html                      <- uso ao vivo
│   ├── absens-apresentacao-executiva.pdf
│   └── cliente/
│       ├── index.html                  <- envio p/ cliente
│       └── absens-apresentacao-executiva-cliente.pdf
└── case-inovacao-publica/
    └── (mesma estrutura)
```

Cada pasta com `index.html` dentro vira uma URL que termina na pasta, sem `.html` à mostra.

## Publicar ou atualizar

**Pela interface do GitHub:** entre na pasta, use *Add file → Upload files* e suba o HTML
renomeado para `index.html` (e o PDF, se houver). O site atualiza em cerca de um minuto.

**Pelo manifesto:** edite o `.assets.json` apontando cada arquivo público para o destino dentro
do repositório. Ao salvar, o workflow baixa e commita sozinho — útil para arquivos grandes, que
a API de conteúdo não aceita direto.

```json
[
  { "dest": "nome-do-deck/index.html", "url": "https://.../deck.html" }
]
```

Depois, ajuste o card correspondente no `index.html` da raiz — título, descrição e, no bloco
`DECKS` do script, o número de slides e o tamanho de cada arquivo das duas versões.

## Regras

- **O link é permanente.** Substituir o `index.html` da pasta atualiza a apresentação sem trocar
  o endereço.
- **Não renomeie a pasta** depois de compartilhar: o nome da pasta é o link.
- **Um deck, um arquivo.** Os HTMLs são autocontidos (fonte, logo e imagens embutidos), então
  não há dependência externa para quebrar e abrem offline por duplo clique.
- Nomes de pasta em minúsculas, com hifens e sem acento.

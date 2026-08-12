# absens-decks

Apresentações HTML do Absens publicadas como páginas web pelo GitHub Pages.

**Endereço do site:** https://nilttonszpak-bec.github.io/absens-decks/

## Como funciona

Cada apresentação vira uma pasta na raiz do repositório, com o HTML dentro chamado `index.html`:

```
absens-decks/
├── index.html                     <- central que lista os decks
├── ciclo-cpsi-recife/
│   └── index.html                 <- https://.../absens-decks/ciclo-cpsi-recife/
└── apresentacao-executiva/
    └── index.html                 <- https://.../absens-decks/apresentacao-executiva/
```

O nome do arquivo `index.html` é o que permite a URL terminar na pasta, sem `.html` à mostra.

## Regras que valem aqui

- **O link é permanente.** Substituir o `index.html` de uma pasta atualiza a apresentação sem trocar o endereço já enviado ao cliente.
- **Um deck, um arquivo.** Os HTMLs são autocontidos (fonte, logo e imagens embutidos), então não há dependência externa para quebrar.
- **Nada de renomear pasta** depois de compartilhar: o nome da pasta é o link.
- **Repositório público.** Qualquer pessoa com a URL abre a apresentação. O `robots.txt` bloqueia buscadores e as páginas trazem `noindex`, então o acesso é por link, não por busca. Nada sob sigilo contratual deve entrar aqui.

## Publicar um deck novo

1. Criar a pasta com o nome que vai virar o link (minúsculas, hifens, sem acento).
2. Subir o HTML da apresentação dentro dela, renomeado para `index.html`.
3. Adicionar o card correspondente no `index.html` da raiz.

A publicação leva cerca de um minuto após o commit.

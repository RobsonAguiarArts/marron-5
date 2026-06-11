# 💘 Contagem regressiva — Maroon 5 no Allianz Parque

Um presente em forma de site: uma página que conta os dias, horas, minutos e segundos
até o show do Maroon 5 em São Paulo (**8 de setembro de 2026, Allianz Parque**) e toca
**uma música diferente da banda a cada dia**, com uma curiosidade nova diariamente.

O fundo é uma **cena de show animada** — holofotes varrendo, plateia com celulares
acesos, partículas de luz e batida pulsando — e ela **muda de cor/clima a cada dia**,
junto com a música. A música aparece como **"tocando agora"**, com um disco de vinil
girando, em vez de um vídeo grande ocupando a tela.

Tudo está em **um único arquivo**: `index.html`. Sem instalação, sem dependências.

---

## 🧪 Testar agora no seu computador

Dê dois cliques no `index.html`. Ele abre no navegador e já funciona.
(A música do dia troca sozinha à meia-noite, no horário do celular de quem abrir.)

---

## ✏️ Personalizar (abra o index.html em qualquer editor de texto)

Procure o bloco `⚙️ PERSONALIZE AQUI`, perto do final do arquivo:

```js
const CONFIG = {
  nomeDela: "",                            // ex.: "Ana" → vira "Para Ana, que vai cantar do começo ao fim"
  dataShow: "2026-09-08T21:00:00-03:00",   // dia e hora do show (mude o 21:00 se quiser outro horário)
  localShow: "Allianz Parque — São Paulo",
  inicioContagem: "2026-06-10",            // dia em que a contagem começou (barra de progresso)
  fotosFundo: [],                          // (opcional) suas fotos no fundo — veja a seção abaixo
};
```

**Coloque o nome dela em `nomeDela`** — fica muito mais especial. 💕

### 🎆 O fundo de show (e como usar SUAS fotos)

Por padrão, o fundo é uma **cena de show animada feita à mão** (holofotes, plateia,
luzes), que muda de cor a cada dia. Não use fotos de shows da banda baixadas da
internet — elas têm direitos autorais. Mas você pode colocar **suas próprias fotos**
(de vocês dois, do casal, do dia que comprou o ingresso…) para passarem no fundo:

1. Coloque os arquivos de imagem **na mesma pasta** do `index.html`.
2. Escreva os nomes na lista `fotosFundo`, por exemplo:
   ```js
   fotosFundo: ["nos-dois.jpg", "viagem.jpg", "show-antigo.jpg"],
   ```
As fotos passam em transição suave, uma após a outra. Se a lista ficar vazia (`[]`),
volta a cena de show animada.

### Trocar ou adicionar músicas

Logo abaixo está a lista `MUSICAS`. Cada linha tem título, álbum e o código do clipe:

```js
{ titulo: "Sugar", album: "V (2014)", yt: "09R8_2nJtjg" },
```

O código `yt` é o que aparece depois de `watch?v=` no link do YouTube.
Exemplo: `youtube.com/watch?v=09R8_2nJtjg` → `yt: "09R8_2nJtjg"`.

As músicas tocam em ciclo, na ordem da lista, uma por dia a partir de `inicioContagem`.
Dica: se quiser que uma música específica caia no dia do show, é só reordenar a lista
(o dia do show usa a posição `91 → índice 6`, ou seja, a 7ª música com a lista de 14).

As curiosidades diárias ficam na lista `FATOS`, logo abaixo — edite à vontade.

---

## 🚀 Publicar na Vercel (de graça)

### Opção A — sem usar terminal (recomendada)

1. Crie uma conta no [github.com](https://github.com) (se ainda não tiver).
2. Clique em **New repository**, dê um nome (ex.: `contagem-maroon5`) e crie.
3. Na página do repositório, clique em **uploading an existing file**, arraste o
   `index.html` (e este README, se quiser) e clique em **Commit changes**.
4. Crie uma conta no [vercel.com](https://vercel.com) usando **Continue with GitHub**.
5. Clique em **Add New… → Project**, escolha o repositório e clique em **Deploy**.
6. Pronto! Em segundos você recebe um link do tipo `contagem-maroon5.vercel.app`.

> O nome do projeto vira o link — vale escolher algo fofo, tipo `faltam-poucos-dias`.

### Opção B — pelo terminal

1. Instale o [Node.js](https://nodejs.org).
2. No terminal, entre na pasta do projeto e rode:
   ```bash
   npx vercel
   ```
3. Faça login (ele manda um link por e-mail) e aceite as opções padrão (Enter, Enter…).
4. Para gerar o link definitivo de produção:
   ```bash
   npx vercel --prod
   ```

### Depois de publicar

- Mande o link pra ela 💌 — o WhatsApp já mostra uma prévia bonitinha do site.
- No celular, dá pra **adicionar à tela de início** (menu do navegador → "Adicionar à
  tela de início"), aí vira um "app" que ela abre todo dia pra ver a música nova.
- Fez alguma mudança no `index.html`? Suba o arquivo de novo no GitHub que a Vercel
  atualiza o site sozinha.

---

## ℹ️ Bom saber

- **Por que a música vem do YouTube?** O arquivo de áudio (MP3) das músicas tem
  direitos autorais — não dá para embutir a faixa "solta" no site sem pirataria. O
  jeito certo e gratuito é usar o player oficial do YouTube. Aqui ele fica **discreto**,
  como um "tocando agora": é só apertar o ▶ e deixar tocar enquanto a cena de show
  preenche a tela. Dá para esconder/mostrar o player com o link abaixo dele.
- **A música não toca sozinha ao abrir** — navegadores bloqueiam áudio automático.
  Ela começa com um toque no play.
- **Quer só áudio, estilo Spotify?** Dá para trocar o player do YouTube por um player
  do Spotify (mostra a capa do álbum e os controles, sem vídeo). Como isso exige pegar
  o link de cada música no Spotify, me peça que eu te passo a versão pronta assim.
- Os 14 clipes são os **oficiais do canal do Maroon 5** no YouTube, então tocam a
  música inteira, de graça.
- O contador usa o horário do aparelho de quem abre; a data alvo já está travada no
  fuso de São Paulo (`-03:00`).
- No dia do show a página muda: chuva de corações, mensagem especial e, depois das
  21h, um "É agora! 🎤". No dia seguinte, ela pergunta se a noite foi incrível. ❤️
- Tem opção de **movimento reduzido**? A página respeita: a cena de show fica parada
  (sem animação) para quem prefere assim.

Bom show pra ela! 🎶
# marron-5

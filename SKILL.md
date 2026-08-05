---
name: criativo-imagem
description: Use SEMPRE que o usuário pedir para gerar, criar ou fazer uma imagem, criativo, anúncio, banner, thumbnail, capa, post ou arte — especialmente quando o pedido for curto e vago ("gera uma imagem de X", "faz um criativo de Y", "cria um anúncio falando Z"). Também use para lotes de criativos, variações de headline e adaptações de formato (feed, story, reels). Transforma briefs vagos em direção de arte completa antes de chamar qualquer modelo de imagem.
metadata:
  version: 1.1.0
---

# Criativo de Imagem — Camada de Direção de Arte

Modelos de imagem não falham por falta de qualidade. Falham por falta de direção.
Um brief de 40 palavras gera resultado genérico. O mesmo brief expandido em direção de
arte gera resultado profissional — **mesmo modelo, mesma conta, mesmo custo.**

Sua função é ser essa camada de expansão. **Nunca mande o pedido cru do usuário para o
modelo de imagem.** Expanda primeiro.

## Regra-mãe

> De um brief vago: infira o **gênero**, e então preencha tudo que aquele gênero espera —
> **inclusive o que não foi pedido.**

Se o usuário disse "anúncio" e não pediu bullets de benefício, logo ou selo — o gênero pede,
então você inclui. Se ele deu um nome de marca, você inventa a identidade visual dela.
Ele contratou o resultado, não a lista de elementos.

## Processo

### 1. Inferir o gênero (a decisão mais importante)

Antes de qualquer coisa, classifique. Pistas: idioma, canal, nicho, ticket, vocabulário.

| Gênero | Pistas | Linguagem visual |
|---|---|---|
| **Direct response BR** | português, "anúncio/tráfego/funil/infoproduto", promessa forte, R$ baixo | preto + 1 cor saturada, caixa alta condensada, palavra-chave em caixa colorida, textura suja/halftone, seta no CTA, bullets com ícone, brilho |
| **SaaS / tech** | inglês ou PT neutro, "ferramenta/plataforma/IA", B2B | fundo off-white, tipografia geométrica bicolor, muito respiro, mockup de device, ícones de linha, faixa de features, sombra suave |
| **E-commerce / produto** | produto físico, preço, "compre/frete" | produto em destaque, fundo limpo ou cena de uso, selo de desconto, preço grande |
| **Luxo / beleza** | skincare, moda, "premium/exclusivo" | paleta neutra dessaturada, serifada fina, muito espaço negativo, luz suave, zero textura |
| **UGC / social** | "depoimento/story/reels", pessoa comum | foto crua de celular, legenda estilo app, cor chapada, imperfeito de propósito |

Na dúvida entre dois: **pergunte ao usuário**, com uma frase cada. Não escolha em silêncio.

**Override explícito.** Se o usuário nomear o gênero ("faz em SaaS clean", "versão direct
response", "estilo luxo"), pule a inferência e use o que ele pediu. O gênero é a alavanca
principal — trocá-lo muda paleta, textura, tipografia e composição de uma vez. Mesmo
conteúdo em gêneros diferentes gera criativos completamente distintos, e isso é a forma
mais barata de testar ângulo visual: mesma copy, dois gêneros, dois criativos pro teste A/B.

### 2. Preencher os 8 slots

Todo prompt final deve conter, explicitamente:

1. **Gênero + canal + formato** — "criativo de anúncio Meta feed, quadrado"
2. **Cena, não objeto** — objeto solto vira clipart. Dê ambiente, hora do dia, luz, profundidade.
   *"coqueiro amarelo"* → *"coqueiro fotográfico real numa praia ao pôr do sol, flare de lente, mar ao fundo"*
3. **Paleta travada em 3 cores** — com hex quando possível. Nunca "colorido".
4. **Composição** — divida o quadro. "Esquerda 45% zona escura de texto, direita 55% foto sangrando."
5. **Hierarquia tipográfica com ênfase diferencial** — quebre a headline em linhas e dê
   tratamento **diferente** por linha. Decida quais 1-2 palavras carregam o soco e destaque-as
   (caixa colorida, vazado, contorno, tamanho).
6. **Elementos de marca** — se houver nome, crie o lockup (selo/ícone + wordmark).
7. **Mobília de persuasão do gênero** — bullets de benefício com ícone, selo de garantia,
   badge, prova. Mesmo sem pedir.
8. **Acabamento** — textura, granulação, halftone, glow, gradiente, sombra. É o que separa
   "gerado por IA" de "feito por designer".

### 3. Travar o texto

Liste cada string entre aspas, exatamente como deve aparecer, e exija acentuação correta.
Termine com: *"All text must be spelled exactly as given, with correct accents, crisp and
perfectly legible. No watermark, no extra text."*

Escreva o prompt **em inglês** com as strings de texto **em português entre aspas** — os
modelos seguem direção de arte melhor em inglês e renderizam as strings literalmente.

### 4. Escolher o modelo

- `gpt_image_2` (quality `high`) — **padrão para anúncio.** Melhor em layout composto,
  tipografia pesada e hierarquia. É o modelo do ChatGPT.
- `nano_banana_pro` — mais clean e arejado; melhor para 4K, diagrama e texto fino.
- `seedream_v5_pro` — edição por instrução sobre imagem existente.
- `soul_2` — pessoas realistas, UGC, retrato.

Sempre `resolution: 2k`, depois reduza para o tamanho de entrega (1080x1080 etc).

### 5. Gerar e verificar

**Uma imagem por brief. Sempre `count: 1`.**
Não gere variações da mesma coisa para o usuário escolher — isso desperdiça crédito e token.
Confie na direção de arte: ela existe justamente para acertar de primeira.
Só gere mais de uma imagem quando o usuário pedir explicitamente variações, ou quando o
brief tiver N copies/ângulos diferentes — aí é **uma imagem por copy**, nunca duas da mesma.

Se o resultado sair errado, **corrija e regere uma**, em vez de gerar várias e escolher.

- **Sempre baixe e olhe o resultado** antes de entregar. Modelos erram acento e cortam texto.
  Não afirme que ficou correto sem ter visto.
- Em lote (10-20 imagens), monte um contact sheet em grade para revisar várias de uma vez
  e só abra em tamanho cheio as suspeitas.

### 6. Salvar

**Um arquivo por imagem, sempre `.jpg`, qualidade 92.**

Nunca salve o mesmo criativo em dois formatos. Nunca deixe o PNG original junto do JPG
final — converta e apague o intermediário. Um criativo = um arquivo.

JPG só não serve quando a imagem precisa de **fundo transparente** (logo, elemento
recortado para composição). Nesse caso use PNG — e aí só o PNG, sem JPG junto.

Nome do arquivo: descritivo e com a variação no nome (`coqueiro-dr-headline-verba.jpg`),
não `imagem_1.jpg`.

## Antes de gerar

Mostre ao usuário **uma linha** com o gênero inferido e a direção escolhida
(ex: *"Lendo como direct response BR — preto/amarelo, caixa alta, textura suja"*).
Se ele discordar, corrige antes de gastar crédito. Não peça aprovação de prompt inteiro.

## Nunca

- Mandar o pedido cru do usuário pro modelo
- Usar "flat vector", "modern", "clean design" como direção — não são direção, são vazio
- Deixar a paleta em aberto
- Entregar sem ter visto a imagem
- **Gerar duas versões da mesma imagem** para o usuário escolher — `count: 1`, sempre
- **Salvar o mesmo criativo em dois formatos** — JPG ou PNG, nunca os dois

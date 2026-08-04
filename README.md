# criativo-imagem

Skill para Claude Code que transforma pedidos vagos de imagem em **direção de arte completa**
antes de chamar qualquer modelo de geração.

Modelos de imagem não falham por falta de qualidade. Falham por falta de direção.

## O problema

Você pede:

> *"gera um anúncio de Meta Ads 1080x1080 de um coqueiro amarelo, falando que a era dos
> anúncios online acabou e que agora o Coqueiro Ads é a verdadeira ferramenta de anúncios,
> com um CTA de saiba mais"*

E recebe isso:

<img src="exemplos/antes-sem-skill.png" width="380">

Está correto. Está legível. E é genérico — não parece um anúncio, parece um slide.

## O que a skill faz

Ela intercepta o pedido e o expande em direção de arte antes de gerar. Mesmo brief, mesmo
modelo, mesmo custo:

| Direct response BR | SaaS / tech |
|---|---|
| <img src="exemplos/direct-response-br.png" width="380"> | <img src="exemplos/saas-tech.png" width="380"> |

**O conteúdo dos dois é idêntico.** Mesma headline, mesma promessa, mesmo CTA. A única
variável que mudou foi o *gênero*.

## A ideia central

> De um brief vago: infira o **gênero**, e então preencha tudo que aquele gênero espera —
> **inclusive o que não foi pedido.**

Se o usuário disse "anúncio" e não pediu bullets de benefício, logo ou selo — o gênero pede,
então você inclui. Se ele deu um nome de marca, você inventa a identidade visual dela.

O gênero é a alavanca principal: trocá-lo muda paleta, textura, tipografia e composição de
uma vez só.

| Gênero | Pistas | Linguagem visual |
|---|---|---|
| Direct response BR | português, "tráfego/funil/infoproduto", promessa forte | preto + 1 cor saturada, caixa alta condensada, textura suja, seta no CTA |
| SaaS / tech | "ferramenta/plataforma/IA", B2B | off-white, tipografia geométrica bicolor, muito respiro, ícones de linha |
| E-commerce | produto físico, preço, frete | produto em destaque, selo de desconto, preço grande |
| Luxo / beleza | skincare, moda, "premium" | neutro dessaturado, serifada fina, espaço negativo, zero textura |
| UGC / social | "story/reels/depoimento" | foto crua de celular, legenda de app, imperfeito de propósito |

Além do gênero, a skill força mais três coisas que fazem a diferença: **cena em vez de
objeto** (um coqueiro vira praia ao pôr do sol, não clipart), **paleta travada em 3 cores com
hex**, e **ênfase diferencial na headline** — decidir quais 1-2 palavras levam o soco e
tratá-las diferente das outras.

## Instalação

**Global** (vale em qualquer pasta):

```bash
git clone https://github.com/AssistenteFlashh007/claude-skill-criativo-imagem
mkdir -p ~/.claude/skills/criativo-imagem
cp claude-skill-criativo-imagem/SKILL.md ~/.claude/skills/criativo-imagem/
```

**Só num projeto:** troque `~/.claude/skills/` por `.claude/skills/` dentro do projeto.

Abra uma sessão nova. A skill dispara sozinha em qualquer pedido de imagem, criativo,
anúncio, banner, thumbnail ou capa — não precisa invocar.

## Uso

Deixe inferir:

```
faz um criativo pro meu curso de tráfego, headline "pare de queimar verba"
```

Ou nomeie o gênero direto:

```
mesma coisa em SaaS clean
agora versão luxo
```

Trocar o gênero mantendo a copy é a forma mais barata de teste A/B visual: a copy fica
travada, então o resultado te diz de verdade a qual linguagem o público responde.

## Requisitos

Um gerador de imagem acessível na sessão — MCP (Higgsfield, Replicate) ou API. A skill
define **como pensar**; ela não embute nenhum provedor. Foi validada com GPT Image 2 e
Nano Banana Pro.

## Licença

MIT

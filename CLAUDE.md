# LP Builder - Sistema de Criação de Landing Pages Low Ticket

## ATIVAÇÃO AUTOMÁTICA OBRIGATÓRIA

**Quando esta pasta for aberta no Claude Code, execute IMEDIATAMENTE sem esperar o usuário digitar nada:**

1. Exibir mensagem de boas-vindas (ver abaixo)
2. Verificar se `output/config.json` existe
3. Se NÃO existe: iniciar o WIZARD DE ENTREVISTA
4. Se JÁ existe: perguntar "Deseja criar uma nova LP ou editar a LP existente?"

---

## MENSAGEM DE BOAS-VINDAS

```
Bem-vindo ao LP Builder!
Vou criar sua Landing Page de Low Ticket agora.
Responda as perguntas e no final você terá um link com sua página pronta.

Qual modo prefere?

MODO RÁPIDO - 5 perguntas (10 minutos, resultado sólido)
MODO EXTREMO - 15 perguntas (25 minutos, página 100% personalizada)

Digite R para Rápido ou E para Extremo:
```

---

## REGRAS DE COMPORTAMENTO

- Fazer UMA pergunta por vez. Nunca várias ao mesmo tempo.
- Aguardar resposta antes de continuar.
- Salvar CADA resposta em `output/config.json` imediatamente após receber.
- Usar linguagem direta, sem enrolação, sem termos técnicos.
- Português brasileiro com acentuação PERFEITA. Zero erros.
- NUNCA exibir código para o usuário durante a entrevista.
- Após a última pergunta: gerar a LP sem perguntar confirmação.

---

## MODO RÁPIDO - 5 PERGUNTAS

### P1 - Identidade
```
Qual é o seu nome e o nome do seu produto ou método?
(Ex: João Silva - Método Clínica Lucrativa)
```

### P2 - Público
```
Quem é o seu público? Qual é a profissão ou nicho deles?
(Ex: dentistas, coaches, advogados, esteticistas, professores)
```

### P3 - Transformação
```
Em UMA frase: qual é o resultado que seu produto entrega?
(Ex: "Dobrar o faturamento do consultório em 90 dias")
```

### P4 - Preço
```
Qual será o preço do produto?

1) R$27
2) R$37 (recomendado)
3) R$47
4) R$67

Digite o número:
```

### P5 - Estilo Visual
```
Qual estilo visual combina com você e seu público?

1) FEMININO SUAVE - rosé, vinho, lilás, fontes elegantes com serifa
2) MASCULINO FORTE - laranja, âmbar, marrom, sem serifa, direto
3) AUTORIDADE - azul navy, dourado, jurídico, profissional
4) TECH MODERNO - roxo, índigo, violeta, futurista
5) SAÚDE & BEM-ESTAR - verde, esmeralda, natural
6) PERSONALIZADO - me diga sua cor favorita

Digite o número:
```

---

## MODO EXTREMO - 15 PERGUNTAS

### BLOCO 1 - IDENTIDADE (P1 a P3) - idêntico ao Modo Rápido

### BLOCO 2 - PROFUNDIDADE DE PÚBLICO

### P4 - Dor Principal
```
Qual é a DOR número 1 do seu público antes de encontrar você?
(Ex: "trabalha muito mas sobra pouco no fim do mês")
```

### P5 - Objeção Principal
```
Qual é a DESCULPA que seu público usa para não investir?
(Ex: "não tenho tempo", "já tentei de tudo", "meu mercado é saturado")
```

### P6 - Diferencial
```
Por que seu método é diferente de tudo que existe no mercado?
Em uma frase, o que só você faz ou ensina?
```

### BLOCO 3 - PROVA E RESULTADO

### P7 - Resultado Concreto
```
Qual é o resultado mais impressionante que um aluno seu obteve?
(Ex: "Aumento de R$30k para R$120k em 4 meses")
Se não tiver alunos ainda, qual resultado VOCÊ obteve?
```

### P8 - Depoimentos
```
Você tem depoimentos ou prints de resultados de alunos?
(Eles serão usados como prova social na página)

1) Sim, tenho vários
2) Sim, tenho 1 ou 2
3) Não tenho ainda

Digite o número:
```

### BLOCO 4 - OFERTA

### P9 - Preço (mesmo do Rápido)
### P10 - Garantia
```
Qual garantia você vai oferecer?

1) 7 dias incondicional (recomendado para low ticket)
2) 15 dias
3) 30 dias
4) Sem garantia

Digite o número:
```

### P11 - Bônus
```
Você vai incluir algum bônus para aumentar o valor percebido?
(Ex: "Planilha de controle financeiro", "Grupo VIP no WhatsApp")
Se sim, diga o nome do bônus. Se não, digite "não":
```

### P12 - Urgência
```
Vai ter algum elemento de urgência ou escassez na página?

1) Vagas limitadas (ex: "somente 200 acessos")
2) Preço por tempo limitado (ex: "oferta por 48h")
3) Bônus por tempo limitado
4) Sem urgência

Digite o número:
```

### BLOCO 5 - IDENTIDADE VISUAL

### P13 - Estilo Visual (mesmo do Rápido)
### P14 - Tipografia
```
Qual sensação você quer transmitir com os títulos?

1) ELEGÂNCIA - fonte com serifa (refinado, premium, sofisticado)
2) FORÇA - fonte sem serifa (moderno, direto, confiante)
3) Deixe o sistema decidir pelo meu estilo

Digite o número:
```

### P15 - Foto
```
Você tem uma foto profissional sua para usar na página?
(Será usada no hero e na seção "Sobre o Especialista")

1) Sim, vou fornecer o caminho do arquivo
2) Não tenho, usar placeholder
```

---

## SALVAMENTO DO CONFIG

Após cada resposta, atualizar `output/config.json`:

```json
{
  "mode": "rapido|extremo",
  "nome_especialista": "",
  "nome_produto": "",
  "nicho": "",
  "transformacao": "",
  "preco": 37,
  "estilo": "feminino|masculino|autoridade|tech|saude|personalizado",
  "cor_personalizada": "",
  "dor_principal": "",
  "objecao": "",
  "diferencial": "",
  "resultado_concreto": "",
  "tem_depoimentos": true,
  "garantia_dias": 7,
  "bonus": "",
  "urgencia": "sem",
  "tipografia": "serifa|sem-serifa|auto",
  "tem_foto": false,
  "caminho_foto": "",
  "status": "coletando|gerando|pronto"
}
```

---

## DESIGN SYSTEM - SISTEMA VISUAL COMPLETO

### FILOSOFIA (NUNCA ALTERAR)
Dark premium + Harmonização monocromática + Textura grain + Copy que converte

- Fundo escuro quase preto tintado na cor principal
- Gradiente dentro de UMA família de matiz (nunca misturar cores incompatíveis)
- Grain overlay para textura premium
- Scroll reveal em todos os elementos (de baixo para cima, nunca lateral)
- Seção clara para quebrar ritmo

### TOKENS CSS BASE (aplicar em :root)

```css
:root {
  --g1:       #XXXXXX;  /* tom escuro da matiz */
  --g2:       #XXXXXX;  /* tom médio - vibrante */
  --g-accent: #XXXXXX;  /* tom claro - highlight */
  --shadow-g: rgba(R,G,B, 0.28);

  --bg:       #050201;  /* quase preto com tint da matiz */
  --bg-alt:   #0C0603;
  --bg-card:  #100805;
  --bg-light: #FFF7ED;  /* seção clara derivada do accent */

  --txt-dark:  #2A1505;
  --txt-light: var(--g-accent);
  --txt-muted: #92400E;

  --red:       #E05252;
  --green-ok:  #4ade80;
  --border:    rgba(R,G,B, 0.14);

  --font-main: /* definida pelo perfil */;
  --font-body: /* definida pelo perfil */;

  --radius:    14px;
  --radius-sm: 8px;
  --transition: 0.3s ease;
  --ease-out:  cubic-bezier(0.16, 1, 0.3, 1);
}
```

### PALETAS POR ESTILO

#### FEMININO SUAVE (rosé marsala)
```css
--g1: #7B3A55; --g2: #C4788E; --g-accent: #EAC4C0;
--shadow-g: rgba(196,120,142,0.22);
--bg: #07040A; --bg-alt: #0C060F; --bg-card: #120810;
--bg-light: #F8EEF0; --txt-dark: #1A0812;
--txt-light: #EAC4C0; --txt-muted: #B090A0;
--font-main: 'Cormorant Garamond', Georgia, serif;
--font-body: 'DM Sans', sans-serif;
Google Fonts: family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300&family=DM+Sans:wght@400;500;600;700;800
```

#### FEMININO ROXO-LILÁS
```css
--g1: #4A2070; --g2: #9B6DBF; --g-accent: #DCC4F0;
--shadow-g: rgba(155,109,191,0.25);
--bg: #060308; --bg-alt: #0A050F; --bg-card: #0F0818;
--bg-light: #F3EEFB; --txt-dark: #1A0830;
--txt-light: #DCC4F0; --txt-muted: #A080C0;
--font-main: 'Cormorant Garamond', Georgia, serif;
--font-body: 'DM Sans', sans-serif;
```

#### FEMININO VINHO-BORGONHA
```css
--g1: #5C1A2A; --g2: #A04060; --g-accent: #E8C0C8;
--shadow-g: rgba(160,64,96,0.25);
--bg: #060204; --bg-alt: #0C0407; --bg-card: #10050A;
--bg-light: #FBF0F2; --txt-dark: #200810;
--txt-light: #E8C0C8; --txt-muted: #B07888;
--font-main: 'Cormorant Garamond', Georgia, serif;
--font-body: 'DM Sans', sans-serif;
```

#### MASCULINO FORTE (laranja-rust)
```css
--g1: #C2400F; --g2: #F97316; --g-accent: #FED7AA;
--shadow-g: rgba(249,115,22,0.35);
--bg: #050201; --bg-alt: #0F0803; --bg-card: #140A04;
--bg-light: #FFF7ED; --txt-dark: #2A1505;
--txt-light: #FEF3E2; --txt-muted: #92400E;
--font-main: 'Inter', system-ui, sans-serif;
--font-body: 'Inter', system-ui, sans-serif;
Google Fonts: family=Inter:wght@300;400;500;600;700;800;900
```

#### AUTORIDADE (dourado-navy)
```css
--g1: #7A4F0D; --g2: #D4A017; --g-accent: #FDE68A;
--shadow-g: rgba(212,160,23,0.30);
--bg: #030305; --bg-alt: #070710; --bg-card: #0C0C18;
--bg-light: #F8F7F0; --txt-dark: #0F0C02;
--txt-light: #FDE68A; --txt-muted: #A08830;
--font-main: 'Inter', system-ui, sans-serif;
--font-body: 'DM Sans', sans-serif;
Google Fonts: family=Inter:wght@300;400;500;600;700;800;900&family=DM+Sans:wght@300;400;500;600;700;800
```

#### TECH MODERNO (roxo-índigo)
```css
--g1: #1E1270; --g2: #6C3AF0; --g-accent: #C4B5FD;
--shadow-g: rgba(108,58,240,0.35);
--bg: #03020A; --bg-alt: #06040F; --bg-card: #0A0716;
--bg-light: #F3F0FF; --txt-dark: #100820;
--txt-light: #C4B5FD; --txt-muted: #8870C0;
--font-main: 'Inter', system-ui, sans-serif;
--font-body: 'DM Sans', sans-serif;
```

#### SAÚDE & BEM-ESTAR (verde-floresta)
```css
--g1: #1A3A2A; --g2: #2D9B60; --g-accent: #A7F3D0;
--shadow-g: rgba(45,155,96,0.28);
--bg: #020604; --bg-alt: #060F08; --bg-card: #091410;
--bg-light: #F0FBF4; --txt-dark: #052010;
--txt-light: #A7F3D0; --txt-muted: #5A9E78;
--font-main: 'Inter', system-ui, sans-serif;
--font-body: 'DM Sans', sans-serif;
```

### TIPOGRAFIA POR ESTILO
| Estilo | font-main | font-body | Headings |
|--------|-----------|-----------|----------|
| Feminino | Cormorant Garamond | DM Sans | weight 300, italic accent |
| Masculino | Inter | Inter | weight 800 |
| Autoridade | Inter | DM Sans | weight 700 |
| Tech | Inter | DM Sans | weight 800, uppercase |
| Saúde | Inter | DM Sans | weight 700 |

### ELEMENTOS VISUAIS OBRIGATÓRIOS

#### Grain Overlay (textura premium - nunca omitir)
```css
body::after {
  content: '';
  position: fixed; inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none; z-index: 999; opacity: 0.45;
}
```

#### Scroll Reveal (de baixo para cima SEMPRE - nunca lateral, nunca blur)
```css
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 1.3s cubic-bezier(0.25,0.46,0.45,0.94),
              transform 1.3s cubic-bezier(0.25,0.46,0.45,0.94);
}
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-stagger > *:nth-child(1) { transition-delay: 0s; }
.reveal-stagger > *:nth-child(2) { transition-delay: 0.12s; }
.reveal-stagger > *:nth-child(3) { transition-delay: 0.22s; }
.reveal-stagger > *:nth-child(4) { transition-delay: 0.32s; }
.reveal-stagger > *:nth-child(5) { transition-delay: 0.42s; }
```
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) e.target.classList.add('visible');
    else e.target.classList.remove('visible');
  });
}, { threshold: 0.08, rootMargin: '0px 0px -40px 0px' });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
```

#### Gradient Text
```css
.grad {
  background: linear-gradient(135deg, var(--g2), var(--g-accent));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  background-clip: text; display: inline;
}
```

#### Botão CTA
```css
.btn-cta {
  display: inline-flex; align-items: center; gap: 10px;
  background: linear-gradient(220deg, var(--g-accent) 0%, var(--g2) 60%, var(--g1) 100%);
  color: #fff; font-weight: 700; font-size: 0.82rem;
  letter-spacing: 0.08em; text-transform: uppercase;
  padding: 20px 44px; border-radius: 4px;
  box-shadow: 0 0 32px var(--shadow-g);
  transition: transform 0.22s ease, box-shadow 0.22s ease, filter 0.22s ease;
  white-space: nowrap; border: none; cursor: pointer;
}
.btn-cta:hover { transform: translateY(-2px); filter: brightness(1.1); }
```

#### Overflow protection (obrigatório)
```css
body { overflow-x: hidden; overflow-wrap: break-word; word-wrap: break-word; }
.sec { overflow: hidden; }
html { scroll-behavior: smooth; }
```

---

## ESTRUTURA DA LP - SEÇÕES OBRIGATÓRIAS (nesta ordem)

```
01. Alert Bar       - urgência/escassez (fundo gradiente g1->g2)
02. Nav             - logo + CTA
03. Hero            - headline + sub + desc + CTA + pills/badges
04. Dor             - "Se você se identifica com..." (bg-alt)
05. Quebra de Crença - o problema real (bg escuro)
06. Mecanismo       - o produto/método (3 cards)
07. Como Funciona   - 3 passos (bg-alt)
08. O Que Vai Receber - 3 itens detalhados
09. Benefícios      - grid 2 col com checks (bg-light - seção clara)
10. Prova Social    - depoimentos (usar placeholder se sem depoimentos)
11. Especialista    - foto + bio + badges
12. Oferta          - checklist + preço riscado + CTA principal
13. Garantia        - X dias incondicional
14. Fechamento      - 2 opções (com/sem) + frase final
15. Footer CTA      - último CTA
```

---

## COPY - PADRÕES DE GERAÇÃO

### Regra Central de Copy Low Ticket
- Copy DIRETA: segmenta pelo NICHO na palavra-chave central
- A palavra-chave do nicho aparece na PRIMEIRA LINHA e no H1 do hero
- Preço SEMPRE visível (nunca esconder)
- NUNCA vender a mentoria na LP (vende o produto baixo)
- Português brasileiro, acentuação perfeita

### Fórmulas de H1 (escolher a mais forte para o nicho)

1. CONTRASTE DOR: "[Nicho], você trabalha [X horas] e sobra quanto?"
2. NÚMERO CHOCANTE: "[Nicho], [resultado impressionante] com [método]"
3. PERGUNTA PROVOCATIVA: "[Nicho], quanto vale [ativo principal] sem você?"
4. PARADOXO: "Agenda cheia e conta no vermelho? O problema não é falta de cliente"
5. COMPARAÇÃO: "Seu concorrente cobra o dobro e tem mais clientes. Sabe por que?"
6. PROVA IMPOSSÍVEL: "[Resultado extremo] em [cidade pequena/cenário difícil]"
7. CRENÇA FALSA: "A mentira que mantém [nicho] preso em [problema]"
8. RESULTADO DIRETO: "De [antes] para [depois] em [tempo]. [Nome método] por R$[preço]"

### Estrutura Hero
```
H1: [fórmula de H1 baseada no nicho e transformação]
H2: [complemento que apoia o H1 sem repetir]
DESC: [2-3 linhas explicando o mecanismo e resultado]
CTA: "Quero [resultado] por R$[preço] →"
PILLS: ["✓ [benefício 1]", "✓ [benefício 2]", "✓ [benefício 3]"]
```

### Seção Dor (3 cards)
```
Card 1: [dor 1 específica do nicho - usar linguagem deles]
Card 2: [dor 2 - consequência da dor 1]
Card 3: [dor 3 - o que eles já tentaram e não funcionou]
```

### Quebra de Crença
```
Título: "O problema não é [o que eles pensam que é]"
Texto: "A verdade é que [crença falsa] → [crença real]"
```

### Mecanismo (3 cards - o produto)
```
Card 1: [módulo/parte 1 do produto] + ícone SVG
Card 2: [módulo/parte 2 do produto] + ícone SVG
Card 3: [módulo/parte 3 do produto] + ícone SVG
```

### Como Funciona (3 passos)
```
Passo 1: "Acesse" - após o pagamento, acesso imediato
Passo 2: "Aprenda" - [ação específica do método]
Passo 3: "Aplique" - [resultado que obtém]
```

### Seção Oferta
```
PREÇO RISCADO: De R$[preço x 3] por
PREÇO REAL: R$[preço] (em branco, nunca gradient)
PARCELAMENTO: ou [parcelas] de R$[valor]
CTA: "Quero [resultado] por R$[preço] →"
```

### Seção Fechamento (2 opções)
```
SEM: "Continua [situação ruim atual]..."
COM: "Com [nome do produto]: [transformação desejada]"
```

### CTA Principal (3 variações - usar a mais forte)
```
1. "Quero [resultado específico] por R$[preço] →"
2. "Acessar [nome produto] por R$[preço] →"
3. "Sim, quero [transformação] →"
```

---

## ÍCONES SVG INLINE (usar nestes cards - stroke-width 1.5, 24x24, sem fill)

```svg
<!-- Livro/Conhecimento -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/></svg>

<!-- Gráfico/Resultado -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>

<!-- Alvo/Foco -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>

<!-- Check/Validação -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>

<!-- Raio/Velocidade -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>

<!-- Chave/Acesso -->
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="m21 2-2 2m-7.61 7.61a5.5 5.5 0 1 1-7.778 7.778 5.5 5.5 0 0 1 7.777-7.777zm0 0L15.5 7.5m0 0 3 3L22 7l-3-3m-3.5 3.5L19 4"/></svg>
```

---

## GERAÇÃO DA LP - PROCESSO OBRIGATÓRIO

### Após coletar todas as respostas:

1. Ler `output/config.json`
2. Selecionar paleta baseada no `estilo`
3. Gerar `output/index.html` completo com:
   - DOCTYPE html, meta charset utf-8, meta viewport
   - Google Fonts corretos para o estilo
   - CSS completo com tokens, grain, reveal, responsivo
   - 15 seções na ordem obrigatória
   - Copy gerada com os padrões deste arquivo
   - LINK REAL de compra: `#comprar` (âncora - instruir o usuário a substituir pelo link da Kiwify/Hotmart)
   - JavaScript com scroll reveal e observer

4. Atualizar `output/config.json` com `"status": "pronto"`

### Qualidade mínima obrigatória antes de entregar:
- [ ] Acentuação perfeita em TODO o texto português
- [ ] Preço em #FFFFFF (nunca gradient)
- [ ] Mobile 375px: nenhum elemento com overflow horizontal
- [ ] CTA principal aparece no hero E na seção de oferta E no footer
- [ ] Grain overlay presente
- [ ] Scroll reveal nas seções
- [ ] Alert bar no topo com urgência (se modo extremo e urgência definida)

---

## PREVIEW E DEPLOY

### Após gerar `output/index.html`:

#### PASSO 1 - Tentar preview via Claude Preview (se disponível)
```
Usar mcp__Claude_Preview__preview_start com output/index.html
```

#### PASSO 2 - Se não tiver preview, iniciar servidor local
```bash
cd output && npx serve -l 3000 .
```
Informar o usuário: "Sua LP está disponível em: http://localhost:3000"

#### PASSO 3 - Se o usuário tiver VPS configurada
Perguntar: "Você tem uma VPS configurada? Se sim, posso fazer o deploy agora para um link permanente."
Se sim: usar o script de deploy configurado pelo usuário.
Se não: "Sua página está pronta em `output/index.html`. Para hospedá-la, você pode usar Netlify (gratuito), Hostinger ou qualquer hospedagem."

---

## REGRAS ABSOLUTAS (nunca violar)

1. NUNCA inventar dados sobre o especialista. Usar apenas o que foi respondido.
2. NUNCA vender mentoria na LP. Vende SEMPRE o produto low ticket.
3. Preço NUNCA com gradient. Sempre em #FFFFFF.
4. Acentuação perfeita: você, não, também, já, só, até, é, está, código, página, título, início, sessão, função, padrão, informação, configuração, conteúdo, módulo, técnico, específico, método, número, possível, ação, criação, solução, versão
5. Zero travessão (—). Usar vírgula ou dois pontos.
6. NUNCA deixar placeholder visível ao usuário (como [NOME] ou [INSERIR AQUI]).
7. Link de compra: usar `#comprar` e instruir usuário a substituir.
8. Hero SEMPRE com background-image ou radial-gradient (nunca layout lado-a-lado).

---

## INSTRUÇÕES PARA QUEM CRIOU ESTE REPOSITÓRIO

Este sistema foi criado pelo AIOS (Synkra). Conteúdo proprietário.
Design System baseado em LPs aprovadas com alta conversão.
Copy frameworks baseados no método Magna/Finch adaptado.

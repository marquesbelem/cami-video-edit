# 🎬 Camis GameDev - Video Edit Workflow (Remotion.dev)

Repositório automatizado para composição, edição programática e pós-produção dos vídeos do canal **Camis GameDev** no YouTube, utilizando [Remotion](https://www.remotion.dev/).

---

## 📁 Estrutura de Pastas

```text
cami-video-edit/
├── gravações/                  # Arquivos brutos de gravação (Entrada)
│   └── video_01/
│       ├── tela.*             # Gravação de captura de tela cheia
│       ├── camera.*           # Gravação da câmera/webcam
│       └── camera_chamada.*   # Gravação de introdução / chamada inicial
│
├── edição/                     # Entregáveis finais gerados (Saída)
│   └── video_01/
│       ├── video_editado.mp4  # Vídeo principal finalizado
│       ├── thumb.png          # Thumbnail personalizada do vídeo
│       ├── short_01.mp4       # 1 Short vertical otimizado
│       └── copy_youtube.md    # Títulos, descrições e SEO (Vídeo + Short)
│
├── exemplos/                   # Referências oficiais de edição e design
│   ├── thumb1.jpg, thumb2.jpg # Referências estéticas para thumbnails
│   └── video1.mp4, video2.mp4 # Referências de ritmo, cortes e layout de vídeo
│
├── intro/                      # Vinhetas e trilhas sonoras oficiais do canal
│   ├── intro_youtube_claro_1920x1080.mp4  # Vinheta YouTube (Tema Claro)
│   ├── intro_youtube_escuro_1920x1080.mp4 # Vinheta YouTube (Tema Escuro)
│   ├── intro_shorts_claro_1080x1920.mp4   # Vinheta Shorts (Tema Claro)
│   ├── intro_shorts_escuro_1080x1920.mp4  # Vinheta Shorts (Tema Escuro)
│   ├── trilha_youtube.wav                 # Trilha sonora oficial para YouTube
│   └── trilha_shorts.wav                  # Trilha sonora oficial para Shorts
│
├── .agent/skills/
│   └── cami-brand-identity/   # Identidade visual oficial e assets da marca
│
├── .agents/skills/
│   ├── youtube-seo/           # Otimização de busca, títulos e descrições
│   └── youtube-shorts/        # Roteirização e composição para Shorts
│
└── README.md                  # Este documento de referência
```

---

## ⚡ Fluxo de Trabalho: Como Iniciar uma Edição (`edit`)

Para iniciar uma nova edição, basta enviar o comando:

> **`edit`**

Ao receber a instrução **`edit`**, o agente assistente obrigatoriamente solicitará as seguintes informações antes de começar:
1. **Identificador da gravação:** Qual pasta de `gravações/` será editada (ex.: `video_01`).
2. **Tema e assunto principal do vídeo:** Contexto sobre o que foi desenvolvido ou ensinado no vídeo.
3. **Corte da chamada & Inserção da intro:** **A partir de qual minuto/segundo deve ser feito o corte da chamada inicial para adicionar a vinheta de intro e depois continuar com o vídeo principal?**
4. **Cortes e minutagens adicionais:** Intervalos ou marcas de tempo (timecodes) para remoções, cortes de erros ou destaques no restante da gravação.

---

## 🎥 Regras de Composição & Edição de Vídeo (Remotion)

### 1. Abertura, Vinheta & Continuação
* O vídeo inicia sempre com o vídeo **`camera_chamada`** atuando como o gancho (hook) inicial.
* No minuto/segundo informado pelo usuário, é realizado o corte onde se insere a **vinheta oficial de intro** localizada em `intro/`:
  * `intro/intro_youtube_claro_1920x1080.mp4` (para vídeos no padrão Tema Claro) ou `intro/intro_youtube_escuro_1920x1080.mp4` (Tema Escuro).
* Após a vinheta de intro, o vídeo **continua com o conteúdo principal** (tela e câmera).

### 2. Composição de Tela & Webcam (Picture-in-Picture)
* O vídeo `tela` é a base da composição e é exibido em **tela cheia** (*full screen* 16:9).
* Quando houver o vídeo `camera`:
  * Deve ser sobreposto em um quadrante menor e visível (ex.: canto inferior ou superior da tela).
  * O quadrante da câmera deve possuir **cantos arredondados** condizentes com a identidade visual da marca e borda sutil de contraste para legibilidade.
  * Não deve cobrir elementos essenciais do código, interface da IDE ou jogo exibido na tela.
  * Remover o ruído de som dos microfones/gravações.

### 3. Elementos Gráficos & Identidade de Layout
* **Referência de Layout da Intro:** Utilizar os elementos gráficos, cores, molduras, cards e transições presentes nos vídeos da pasta `intro/` como base de inspiração e padrão de layout para todos os elementos visuais inseridos durante o vídeo (lower-thirds, caixas de destaque, cards informativos e overlays).
* **Visibilidade do Logo Camis GameDev:** Sempre que o logotipo da Camis GameDev aparecer nas edições (overlays, vinhetas, badges, cantos de tela ou encerramentos), ele deve estar em um **tamanho bom, bem visível, nítido e legível**, nunca excessivamente diminuto ou imperceptível.
* **Referências da pasta `exemplos/`:** Seguir o padrão de ritmo, dinamismo e estilo demonstrado nos vídeos de referência `exemplos/video1.mp4` e `exemplos/video2.mp4`.

### 4. Áudio & Trilhas Sonoras Oficiais
* **Tratamento de Áudio da Câmera (Filtro de Ruído & Destaque de Voz):** Antes de utilizar o vídeo da câmera (`camera_chamada`, `camera`, etc.), aplicar obrigatoriamente um filtro de redução de ruído (denoise / noise suppression) para eliminar chiados de microfone/ambiente e destacar a voz com clareza.
* **Trilha Sonora em Estilo Lofi:** A trilha sonora de fundo enquanto o vídeo está passando deve ser no estilo **lofi**, mantida em volume suave para não competir com a fala.
* Utilizar as trilhas sonoras oficiais disponibilizadas na pasta `intro/`:
  * `intro/trilha_youtube.wav` para os vídeos principais do YouTube.
  * `intro/trilha_shorts.wav` para os vídeos Shorts.
* **REGRA INEGOCIÁVEL:** Todas as trilhas e efeitos devem ser **100% livres de direitos autorais (Royalty-Free / No Copyright)**, garantindo que o canal permaneça totalmente elegível à monetização no YouTube.

---

## 📱 Regras Específicas para YouTube Shorts

1. **Composição Equilibrada (Tela + Câmera):**
   * O layout do Short vertical (1080x1920 - 9:16) deve **sempre conter uma parte significativa do vídeo `tela` combinada com o vídeo `camera_chamada`** (ex.: divisão dinâmica de tela ou Picture-in-Picture vertical generoso), permitindo que o público veja tanto as reações e explicações da criadora quanto a prática acontecendo na tela.
2. **Vinheta no Final:**
   * Obrigatoriamente, no **final do Short**, inserir a vinheta oficial de encerramento de Shorts:
     * `intro/intro_shorts_claro_1080x1920.mp4` ou `intro/intro_shorts_escuro_1080x1920.mp4`.
3. **Áudio do Short:**
   * Utilizar a trilha sonora `intro/trilha_shorts.wav`.
4. **Estratégia de Retenção:**
   * Gancho nos primeiros 3 segundos para evitar o swipe, ritmo acelerado e texto dinâmico na tela conforme as diretrizes da skill `youtube-shorts`.

---

## 🖼️ Regras para Criação de Thumbnails (`thumb.png`)

* **Referência Estrita:** Utilizar obrigatoriamente como referência de design, tipografia, contraste e estilo visual as imagens de exemplo da pasta `exemplos/`:
  * `exemplos/thumb1.jpg`
  * `exemplos/thumb2.jpg`
* **Especificações:**
  * Resolução: 1280x720 (16:9).
  * Alto contraste, tipografia legível mesmo em telas mobile pequenas, cores temáticas da Camis GameDev e elementos de foco que resumam o gancho do vídeo.
  * **Proibição Absoluta:** NÃO utilizar inteligência artificial para gerar rostos de pessoas sintéticas. Utilizar apenas recortes reais das gravações e assets oficiais da marca.

---

## 🎨 Identidade Visual da Marca (`cami-brand-identity`)

Sempre que realizar uma edição, o assistente deve consultar e aplicar a skill `cami-brand-identity` para elementos visuais:

* **Paleta de Cores e Temas:**
  * **Padrão:** **Light Mode** (com suporte a Dark Mode quando solicitado).
  * Aplicar as paletas oficiais conforme o assunto do vídeo:
    * *Dark Blue / Neon Blue:* Unity 3D, engenharia, C#, tutoriais avançados.
    * *Roblox Crimson:* Roblox Studio, Luau e desenvolvimento para público jovem.
    * *Scratch Orange:* Lógica para iniciantes, visual scripting e alfabetização digital.
* **Rounded Design System:** Todos os cards, lower-thirds, caixas de código, moldura da câmera e botões devem usar bordas generosamente arredondadas (`border-radius` pill ou squircle).
* **Assinatura Obrigatória no Rodapé:**
  * Todos os layouts de encerramento ou telas de crédito devem conter a assinatura oficial:
    `Desenvolvido por Camis GameDev (http://cmbelem.vercel.app/)`
* **Assets Oficiais:** Utilizar logos e símbolos disponíveis em `.agent/skills/cami-brand-identity/assets/`.
* ⚠️ **Atenção sobre Gamificação:** A parte de **gamificação** contida na skill `cami-brand-identity` deve ser **ignorada** durante o fluxo de edição de vídeo até que seja expressamente solicitada.

---

## 📦 Entregáveis Obrigatórios da Edição

Toda edição executada deve salvar seus resultados dentro de `edição/<subpasta_do_video>/` (ex.: `edição/video_01/`), contendo:

1. **Vídeo Completo Editado (`video_editado.mp4`):**
   * Composição completa: gancho inicial (`camera_chamada`), corte com a vinheta da pasta `intro/`, continuidade com `tela` full e `camera` PiP com cantos arredondados, cortes aplicados, trilha oficial `intro/trilha_youtube.wav` e áudio sem ruído.
2. **Thumbnail do Vídeo (`thumb.png`):**
   * Imagem em alta resolução (1280x720) baseada nas referências `exemplos/thumb1.jpg` e `exemplos/thumb2.jpg`.
3. **1 Short Vertical (`short_01.mp4`):**
   * Vídeo 9:16 combinando de forma significativa `tela` e `camera_chamada`, encerrando com a vinheta `intro/intro_shorts_*.mp4` e trilha `intro/trilha_shorts.wav`.
4. **Copy & SEO Completo para YouTube (`copy_youtube.md`):**
   * Gerado utilizando a skill `youtube-seo`.
   * **Para o Vídeo Longo:**
     * Opções de títulos com alto CTR e potencial de busca (< 60 caracteres).
     * Descrição otimizada (primeiras linhas de gancho, sumário/capítulos com minutagem, links sociais e hashtags).
     * Tags e palavras-chave sugeridas.
   * **Para o Short:**
     * Título impactante com gancho forte.
     * Descrição curta e hashtags específicas (`#Shorts`, tópicos de gamedev).

---

## 🛡️ Guardrails e Regras Estritas de Imagem & Privacidade

> [!CAUTION]
> **DIRETRIZ DE PROTEÇÃO DE IMAGEM E RECURSOS PRÓPRIOS:**
> 
> 1. **NÃO gerar fotos, avatares ou vídeos de outras pessoas através de inteligência artificial.**
> 2. **NÃO gerar pessoas sintéticas nem representações sintéticas por IA da imagem da dona do canal (Camis).**
> 3. Utilizar **EXCLUSIVAMENTE** os recursos autênticos disponibilizados neste projeto:
>    * Os próprios vídeos gravados (`gravações/`);
>    * Frames e capturas extraídos das próprias gravações;
>    * Assets oficiais fornecidos em `.agent/skills/cami-brand-identity/assets/` (logotipos, ícones, fontes);
>    * Referências e vinhetas das pastas `exemplos/` e `intro/`.
> 
> O objetivo deste projeto é dar suporte operacional e agilidade na edição e pós-produção dos próprios vídeos reais da criadora.

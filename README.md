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
│       └── camera_chamada.*   # Gravação de introdução / gancho (hook)
│
├── edição/                     # Entregáveis finais gerados (Saída)
│   └── video_01/
│       ├── video_editado.mp4  # Vídeo principal finalizado
│       ├── thumb.png          # Thumbnail personalizada do vídeo
│       ├── short_01.mp4       # 1 Short vertical otimizado
│       └── copy_youtube.md    # Títulos, descrições e SEO (Vídeo + Short)
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

Ao receber a instrução **`edit`**, o agente assistente obrigatoriamente solicitará as informações necessárias antes de começar:
1. **Identificador da gravação:** Qual pasta de `gravações/` será editada (ex.: `video_01`).
2. **Tema e assunto principal do vídeo:** Contexto sobre o que foi desenvolvido ou ensinado no vídeo.
3. **Cortes e minutagens:** Intervalos ou marcas de tempo (timecodes) para remoções, cortes de erros ou destaques, caso haja.

---

## 🎥 Regras de Composição & Edição de Vídeo (Remotion)

### 1. Abertura Obrigatória (Intro)
* O vídeo **sempre inicia** utilizando o arquivo gravado em `camera_chamada`.
* A intro atua como o gancho (hook) para prender a atenção da audiência antes da vinheta ou da transição para a tela principal.

### 2. Composição de Tela & Webcam (Picture-in-Picture)
* O vídeo `tela` é a base da composição e é exibido em **tela cheia** (*full screen* 16:9).
* Quando houver o vídeo `camera`:
  * Deve ser sobreposto em um quadrante menor e visível (ex.: canto inferior ou superior da tela).
  * O quadrante da câmera deve possuir **cantos arredondados** condizentes com a identidade visual da marca e borda sutil de contraste para legibilidade.
  * Não deve cobrir elementos essenciais do código, interface da IDE ou jogo exibido na tela.

### 3. Áudio, Trilha Sonora & Efeitos Sonoros (SFX)
* Incluir música de fundo (background music) suave e efeitos sonoros pontuais em transições e momentos de ênfase.
* **REGRA INEGOCIÁVEL:** Todas as trilhas e efeitos devem ser **100% livres de direitos autorais (Royalty-Free / No Copyright)**, garantindo que o canal permaneça totalmente elegível à monetização no YouTube.

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
   * Composição completa com intro (`camera_chamada`), cortes aplicados, sobreposição da webcam sobre a tela e trilha de fundo sem copyright.
2. **Thumbnail do Vídeo (`thumb.png`):**
   * Imagem de alta resolução (1280x720) orientada ao tema e conteúdo do vídeo, aplicando a identidade visual e legibilidade para miniatura no YouTube.
3. **1 Short Vertical (`short_01.mp4`):**
   * Corte no formato 9:16 (1080x1920) extraindo o momento de maior impacto, dica rápida ou gancho do vídeo longo, gerado utilizando a skill `youtube-shorts`.
4. **Copy & SEO Completo para YouTube (`copy_youtube.md`):**
   * Gerado utilizando a skill `youtube-seo`.
   * **Para o Vídeo Longo:**
     * Opções de Títulos com alto CTR e potencial de busca.
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
>    * Assets oficiais fornecidos em `.agent/skills/cami-brand-identity/assets/` (logotipos, ícones, fontes).
> 
> O objetivo deste projeto é dar suporte operacional e agilidade na edição e pós-produção dos próprios vídeos reais da criadora.


# Operação OAB — Landing page

Landing page do curso **Operação OAB — 2ª Fase Direito Penal** (Prof. Norton Viggiano), com checkout Hotmart embutido, contador de oferta, cupom OPERACAO10 e Pixel da Meta.

Site estático: HTML, CSS e JavaScript puros, sem build.

## Estrutura

- `index.html` — a página inteira (estilos e scripts inclusos).
- `assets/` — logos e mockup otimizados (WebP, com PNG/JPEG de reserva).
- `design/` — pacote original exportado do Claude Design (protótipo, conversa e arquivos da marca).

## Configuração

No fim do `index.html`, no bloco `CONFIG`:

| Campo | O que é |
|---|---|
| `checkoutUrl` | Link do checkout Hotmart |
| `price` | Preço cheio em R$ (o cupom aplica `discount`) |
| `videoUrl` | Link do YouTube ou Vimeo da VSL; vazio esconde o vídeo |
| `timerHours` | Duração do contador; recomeça a cada vez que a página abre |
| `deadline` | Data limite do contador (23:59:59, horário de Brasília) |

## Pixel da Meta

ID `1076361875004041`. Eventos enviados pela página: `PageView`, `ViewContent` (ao ver a oferta) e `InitiateCheckout` (ao clicar em "Garantir minha vaga"). O `Purchase` deve ser configurado na Hotmart, em Ferramentas → Pixel.

## Publicar

Qualquer hospedagem estática serve. No GitHub Pages: Settings → Pages → Deploy from a branch → `main` / `(root)`.

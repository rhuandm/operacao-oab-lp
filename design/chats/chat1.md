# Landing page Hotmart com desconto

_Started 2026-09-23 01:39 UTC_

---

## User

quero desenvolver uma landing page para esse curso, vamos integrar o checkout do hotmart. a LP deve ser leve, rápida e comercial, desenvolvida 100% para conversão. Podemos trabalhar com um contador de tempo, para uma promoção especial limitada de 10% OFF com o CUPOM: OPERACAO10.

## User

quero desenvolver uma landing page para esse curso, vamos integrar o checkout do hotmart. a LP deve ser leve, rápida e comercial, desenvolvida 100% para conversão. Podemos trabalhar com um contador de tempo, para uma promoção especial limitada de 10% OFF com o CUPOM: OPERACAO10.

## Assistant



## Assistant

_[tool: list_files]_

_[tool: read_skill_prompt]_

_[tool: run_script]_

_[tool: copy_files]_

Names may be NFD-encoded.

_[tool: run_script]_

_[tool: run_script]_

_[tool: copy_files]_

_[tool: copy_files]_

_[tool: run_script]_

_[tool: run_script]_

_[tool: ask_user]_

Li o manual de marca. Para montar a LP, preciso de algumas informações no formulário: preço, link do checkout Hotmart, tipo de contador e o material que você já tem. O que você pular, eu preencho com espaços editáveis para trocar depois.

## User

Answered — price: 375; checkout: <script type="text/javascript">
	function importHotmart(){ 
 		var imported = document.createElement('script'); 
 		imported.src = 'https://static.hotmart.com/checkout/widget.min.js'; 
 		document.he…; coupon_mode: Mostrar cupom para o aluno copiar; timer: Evergreen por visitante (ex: 24h desde a 1ª visita); deadline: 30/09/2026; checkout_embed: Checkout embutido na página (widget Hotmart); assets: Vídeo de vendas (VSL), Garantia (7 dias)

## Assistant

_[tool: copy_files]_

_[tool: delete_file]_

_[tool: dc_write]_

_[tool: ready_for_verification]_

A LP está pronta para revisão: `Operacao OAB - LP.dc.html`.

Faltam três coisas para ela funcionar de verdade:
- **Link do checkout:** o código da Hotmart que você colou chegou cortado, sem o link `pay.hotmart.com/...`. Coloque esse link no painel de Tweaks, em "Checkout". O botão já abre o checkout da Hotmart na própria página, mas ainda não testei isso ao vivo.
- **Vídeo de vendas:** cole o link do YouTube ou do Vimeo em "Vídeo".
- **Garantia de 7 dias:** escrevi o texto como garantia incondicional com reembolso de 100%. Confirme se é essa a política.

Como ficou:
- **Preço:** R$ 375,00 riscado, R$ 337,50 com o cupom OPERACAO10 e um botão para copiar o cupom.
- **Contador:** 24h a partir da primeira visita de cada pessoa, mas nunca passa de 30/09/2026 às 23:59. Dá para mudar as horas e a data nos Tweaks.

**Outros pontos:**
- As fontes do manual (FreeSerif e Neulis Sans) não existem no Google Fonts, então usei Tinos e Outfit, que são parecidas.
- Os textos de "Para quem é" e do FAQ saíram do manual de marca. Revise, principalmente a parte de formas de pagamento.
- Se quiser, posso incluir depoimentos, foto e bio do professor quando você tiver esse material.

## User

no caso, vamos colocar o widget da hotmart no site. segue;


<script type="text/javascript">
	function importHotmart(){ 
 		var imported = document.createElement('script'); 
 		imported.src = 'https://static.hotmart.com/checkout/widget.min.js'; 
 		document.head.appendChild(imported); 
		var link = document.createElement('link'); 
		link.rel = 'stylesheet'; 
		link.type = 'text/css'; 
		link.href = 'https://static.hotmart.com/css/hotmart-fb.min.css'; 
		document.head.appendChild(link);	} 
 	importHotmart(); 
 </script> 
 <a onclick="return false;" href="https://pay.hotmart.com/O107585601B?checkoutMode=2" class="hotmart-fb hotmart__button-checkout"><img src='https://static.hotmart.com/img/btn-buy-green.png'></a>

## Assistant

_[tool: dc_js_str_replace]_

_[tool: dc_js_str_replace]_

_[tool: dc_js_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: dc_set_props]_

_[tool: ready_for_verification]_

O widget da Hotmart está integrado na página, com o seu código O107585601B. O botão "Garantir minha vaga" agora deve abrir o checkout da Hotmart por cima da página, sem sair do site. Ainda não testei esse clique ao vivo.

Mantive o botão vermelho da marca no lugar do botão verde padrão da Hotmart. Se a folha de estilo da Hotmart mudar a aparência do botão, me avise que eu ajusto.

## User

Found issues — fixing…

## Assistant

_[tool: dc_html_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

A folha de estilo da Hotmart estava deixando o botão principal com borda e sombra verdes, cantos arredondados e fonte Helvetica. Ajustei para ele voltar ao visual da marca: vermelho, cantos retos e fonte Outfit. O widget e o link do checkout continuam os mesmos. A página está em revisão de novo.

## User

nao está abrindo o widget

## Assistant

_[tool: eval_js_user_view]_

_[tool: eval_js_user_view]_

The cause was my own click handler: it cancelled the click before Hotmart's widget could open. Removing it.

_[tool: dc_html_str_replace]_

_[tool: dc_js_str_replace]_

_[tool: eval_js_user_view]_

_[tool: eval_js_user_view]_

_[tool: dc_js_str_replace]_

_[tool: dc_html_str_replace]_

_[tool: eval_js_user_view]_

_[tool: eval_js_user_view]_

O widget agora abre. Cliquei em "Garantir minha vaga" no seu preview e o checkout da Hotmart (O107585601B) abriu por cima da página.

O problema era que a página redesenha o botão, e o widget da Hotmart perdia a ligação com ele. Agora o próprio botão chama o widget, então isso não acontece mais.

No celular, o botão leva direto para a página de checkout da Hotmart, sem abrir por cima. É o mesmo comportamento padrão do código da Hotmart.

## User

quero que coloque que termina em 2 horas

## Assistant

_[tool: dc_js_str_replace]_

_[tool: dc_set_props]_

O contador agora vai de 2 horas, contadas a partir da primeira visita de cada pessoa. Como você já tinha aberto a página antes, no seu navegador o tempo restante conta desde aquela primeira visita.

Quando as 2 horas acabam, o contador para em 00:00:00 e o cupom continua aparecendo. Quer que ele reinicie sozinho ou que a oferta suma quando zerar?

## User

show. neste site conseguimos colocar pixel?

## Assistant

Sim, dá para colocar. Eu instalo na página o código base do pixel, que registra as visitas, e crio eventos nos cliques. Com o Meta, por exemplo:

- **PageView:** registrado assim que a página abre.
- **ViewContent:** quando o visitante chega na seção da oferta.
- **InitiateCheckout:** quando ele clica em "Garantir minha vaga".
- **Purchase:** esse não vem da página, porque a compra acontece dentro do checkout da Hotmart. Você configura no painel da Hotmart, em Ferramentas → Pixel, com o mesmo ID do pixel.

O mesmo vale para o Google Tag Manager, o Google Ads/GA4 e o TikTok.

Me mande o ID do pixel e diga quais plataformas quer usar.

## User

quero adicionar esse mockup que mostra nossa área de membros, em uma seção para isso. copy;

AULAS NOVAS TODOS OS DIAS.

Você não recebe todo o conteúdo de uma vez.

A Operação foi estruturada para liberar novas aulas diariamente, mantendo seu estudo organizado e fazendo você avançar passo a passo até a prova.

## Assistant

_[tool: copy_files]_

_[tool: dc_html_str_replace]_

_[tool: ready_for_verification]_

Adicionei a seção da área de membros logo depois de "O método", em fundo branco. O texto está exatamente como você mandou, com "AULAS NOVAS TODOS OS DIAS." numa etiqueta vermelha em cima do título, e o mockup do notebook e do celular vem logo abaixo.

## User

quanto esta no modo celular o checkou abre uma nova pagina, será que seria possivel nao abrir uma nova pagina e sim abrir na mesma?

## Assistant

_[tool: dc_js_str_replace]_

_[tool: ready_for_verification]_

Agora, no celular, o checkout abre por cima da página em tela cheia, com um "×" para fechar, e o visitante não sai do site. No computador continua igual.

Não testei essa mudança num celular de verdade. Vale fazer uma compra de teste no seu aparelho: alguns navegadores de celular podem bloquear o pagamento dentro da janela, principalmente com cartão salvo no Apple Pay ou no Google Pay. Se isso acontecer, volto a abrir o checkout na página da Hotmart só no celular.


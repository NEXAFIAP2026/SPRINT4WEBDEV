# EDITAI com Nexa — Sprint 4


## Links de avaliação

- Repositório Git: https://github.com/NEXAFIAP2026/SPRINT4WEBDEV
- Deploy na Vercel: https://vercel.com/gabrielpf2008-commits/sprint4webdev/FFy4dYjeS2ECUVaCMhaq2s85Wp3E

(Não conseguimos fazer o Vercel funcionar, tentamos de tudo inclusive Ia e ele da o erro 404 em nossos computadores)

O código está preparado para a Vercel, mas preparação não equivale a publicação. Consulte o passo a passo abaixo para concluir o deploy e registrar a URL.


## Funcionalidades

1. Navegue pelas três paisagens da galeria original ou importe uma foto JPG, PNG ou WebP de até 12 MB e 24 megapixels.
2. Escolha um estilo ou escreva uma intenção direta, como `quero algo quente`.
3. Ajuste iluminação, contraste, saturação, tons quentes, matiz e preto e branco pelos controles.
4. Alterne entre original e resultado. Os ajustes são aplicados ao Canvas, sem alterar o arquivo original.
5. Consulte uma paleta online e toque em uma cor para aplicar uma tonalidade suave de 15%. Essa tonalidade pode ser removida.
6. Dê um nome e baixe o PNG processado. O maior lado é limitado a 2000 px para manter o protótipo leve.
7. Salve uma miniatura e os parâmetros no histórico. Abra o histórico para buscar, inspecionar, excluir registros e exportar JSON.

O histórico tem limite de 30 registros e pertence ao navegador/origem em uso. Mudar de computador, domínio ou navegador não transfere os dados. A sessão de demonstração não cria perfis separados de armazenamento. O JSON contém miniaturas e parâmetros, sem as imagens completas; para preservá-las, baixe o PNG. A exportação JSON não possui importação/restauração pela interface nesta versão. Dados inválidos são preservados e uma mensagem orienta a exportação ou exclusão deliberada.


## API externa

O botão Consultar paleta online realiza um `fetch` HTTPS para The Color API:


https://www.thecolorapi.com/scheme?hex=336699&mode=complement&count=3


`hex` é substituído pela cor média da foto original, calculada localmente. Só essa cor é enviada, não a imagem. O código verifica status HTTP, quantidade de cores, hexadecimal e nome. O hook usa timeout de oito segundos e AbortController para cancelar consultas antigas. O usuário vê estados de carregamento, erro e nova tentativa pelo mesmo botão. Não há paletas inventadas como fallback. A disponibilidade e o CORS do serviço dependem do provedor.

Documentação: https://www.thecolorapi.com/docs

## Uso de inteligência artificial no projeto

A IA foi utilizada como apoio ao desenvolvimento para analisar os dois projetos da Sprint 3, integrar a landing page ao React, auxiliar na organização dos componentes e hooks, adaptar o layout ao Tailwind, revisar o tratamento de erros e elaborar testes e documentação. O grupo deve revisar e compreender o código antes da apresentação. Na aplicação, a Nexa funciona por regras de palavras-chave, não por um modelo de IA treinado ou generativo: reconhece intenções como vibrante, sombrio, quente e esverdeado e escolhe parâmetros predefinidos. A análise da cor média serve à consulta de paletas, sem reconhecimento de objetos ou compreensão semântica da cena.

Ps: Usamos Vite pq estamos mais familiarizados do que com Next :/

## Responsividade e acessibilidade

O layout utiliza grids e flexbox com breakpoints do Tailwind. As páginas são adaptadas para celular, tablet e desktop. O menu mobile possui estado expandido, os campos têm labels, os botões têm foco visível e os erros/status usam regiões acessíveis. Existe link para pular ao conteúdo e respeito à preferência por movimento reduzido. A comparação é controlada por botão, sem exigir gesto de arrastar.

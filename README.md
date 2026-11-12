Instruções da atividade 15 :

Projeto de Automação E2E - RetailTech Solutions com Cypress

Este repositório contém a suíte de testes automatizados End-to-End (E2E) desenvolvida em Cypress para a aplicação Automation Test Store (https://automationteststore.com/), atendendo rigorosamente aos requisitos de qualidade da RetailTech Solutions (coordenando navegação, catálogo, carrinho, formulários e responsividade).

1. Pré-requisitos e Instalação

Pré-requisitos do Ambiente

O projeto foi desenvolvido para ser executado em ambientes Node.js e sistemas Linux (como o GitHub Codespaces).
Caso esteja a executar num ambiente Linux sem interface gráfica (headless), é necessário instalar as dependências de sistema para suporte ao browser do Cypress (incluindo compatibilidade com pacotes do Ubuntu 24.04):

sudo dpkg --add-architecture amd64 && sudo apt-get update && sudo apt-get install -y libasound2t64 libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libnss3 libnspr4 libx11-xcb1 libxtst6 xauth xvfb


Instalação do Projeto

Clone o repositório público:

git clone https://github.com/VOX970/retailtech-cypress-entrega.git


Aceda ao diretório do projeto:

cd retailtech-cypress-entrega


Instale as dependências do Node.js:

npm install


2. Execução dos Testes

Para executar toda a suíte de testes em modo headless (via terminal):

npm run cy:run


Para abrir a interface gráfica iterativa do Cypress:

npm run cy:open


3. Descrição dos Testes Implementados

A suíte contempla 17 cenários automatizados End-to-End (E2E) distribuídos entre os 5 módulos funcionais exigidos pelo projeto:

1. Navegação e Organização da Interface (cypress/e2e/navigation.cy.js)

Navegação de Categoria (Positivo): Valida a navegação da página inicial para categorias específicas (ex: Skincare) e verifica o carregamento da URL e do título da página.

Exibição de Produtos (Positivo): Valida se a seleção de categorias exibe os itens comerciais correspondentes.

Retorno à Página Inicial (Positivo): Valida o uso do logotipo e links de navegação para retornar à home.

Estados do Menu (Comportamento): Valida os comportamentos e estados do menu principal após interações de hover e clique.

2. Catálogo e Apresentação de Produtos (cypress/e2e/catalogo.cy.js)

Informações Essenciais (Positivo): Verifica se a listagem apresenta corretamente nomes, preços e imagens dos produtos.

Página de Detalhes (Positivo): Valida a navegação da listagem para a página de detalhes de um item específico.

Busca de Produtos (Negativo): Valida o comportamento da barra de busca ao procurar por um produto inexistente, exibindo a mensagem apropriada na interface.

Consistência Comercial (Consistência): Valida se o preço exibido na listagem de produtos coincide exatamente com o preço apresentado na página de detalhes.

3. Gerenciamento do Carrinho (cypress/e2e/carrinho.cy.js)

Inclusão no Carrinho (Positivo): Valida a adição bem-sucedida de um produto ao carrinho de compras.

Atualização e Recálculo (Positivo): Valida a alteração de quantidades de itens no carrinho e o recálculo correspondente dos valores.

Remoção e Carrinho Vazio (Comportamento): Valida a exclusão de itens e a mensagem correta de interface quando o carrinho está vazio.

Tentativa de Quantidade Inválida (Negativo): Valida o comportamento da interface ao tentar submeter quantidades nulas ou inválidas.

4. Formulários e Validação de Interface (cypress/e2e/formularios.cy.js)

Campos Obrigatórios Ausentes (Negativo): Valida o comportamento do formulário de contato sem o preenchimento dos campos exigidos.

Erro de Credenciais / Autenticação (Negativo): Valida a exibição de alertas de erro ao tentar submeter formulários de login sem dados válidos.

Mensagens de Orientação (Comportamento): Valida a apresentação de telas de suporte e orientação ao iniciar fluxos de cadastro.

5. Responsividade e Experiência de Navegação (cypress/e2e/responsividade.cy.js)

Disponibilidade do Menu Mobile (Responsividade): Valida a visibilidade e o comportamento dos elementos de navegação em resoluções simuladas (viewport iphone-xr).

Busca e Carrinho em Mobile (Responsividade): Valida a usabilidade e o acesso à barra de busca e ao carrinho de compras em dispositivos móveis.

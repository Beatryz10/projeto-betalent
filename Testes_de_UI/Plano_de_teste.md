# Plano de Testes - UI Testing

## Introdução
Este documento descreve o plano de testes para a validação da plataforma de e-commerce Sauce Demo.

## Objetivo
Validar os principais fluxos da plataforma de e-commerce Sauce Demo para garantir a funcionalidade, usabilidade e qualidade antes do lançamento em produção.


## Escopo
Os testes cobrem os principais fluxos descritos no desafio, incluindo login, ordenação de produtos, fluxo de compra e outros.

## Estratégia de Teste
- Testes manuais em navegadores Chrome e Firefox.
- Testes realizados em diferentes tamanhos de tela (desktop e mobile).
- Identificação de problemas de UX/UI que podem impactar a experiência do usuário.

## Ferramentas
- Browser: Chrome, Edge
- Captura de tela: visbug
- Gerenciamento de bugs: Documentação em Markdown


## Cenários de Teste

## Login

### CT-001: Login com usuário padrão
**Descrição:** Validar login com o usuário padrão.  
**Pré-condição:** Acessar [Sauce Demo](https://www.saucedemo.com).  
**Passos:**  
1. Insira o nome de usuário "standard_user".  
2. Insira a senha "secret_sauce".  
3. Clique no botão "Login".  

**Resultado esperado:** O usuário é redirecionado para a página inicial da loja e o título "Products" é exibido.

**Status:** 
Passou ✅

---

### CT-002: Login com senha inválida
**Descrição:** Validar login com senha inválida.  
**Pré-condição:** Acessar [Sauce Demo](https://www.saucedemo.com).  
**Passos:**  
1. Insira o nome de usuário "locked_out_user".  
2. Insira a senha "123qwe.".  
3. Clique no botão "Login".  

**Resultado esperado:** Uma mensagem de erro **"Epic sadface: Username and password do not match any user in this service."** é exibida.

**Status:**
Passou ✅

---

### CT-003: Login com usuário inválido
**Descrição:** Validar login com o usuário inválido.  
**Pré-condição:** Acessar [Sauce Demo](https://www.saucedemo.com).  
**Passos:**  
1. Insira o nome de usuário "locked_user".  
2. Insira a senha "123qwe.".  
3. Clique no botão "Login".  

**Resultado esperado:** Uma mensagem de erro **"Epic sadface: Username and password do not match any user in this service"** é exibida.

**Status:**
Passou ✅

---

### CT-004: Login com usuário e senha vazios
**Descrição:** Validar login com usuário e senha vazios.  
**Pré-condição:** Acessar [Sauce Demo](https://www.saucedemo.com).  
**Passos:**  
1. Deixe o nome de usuário vazio.  
2. Deixe a senha vazia.  
3. Clique no botão "Login". 

**Resultado esperado:** A mensagem **"Epic sadface: Username is required"** é exibida.

**Status:**
Passou ✅

---

### CT-005: Tempo de carregamento do login
**Descrição:** Validar carregamento do login.  
**Pré-condição:** Acessar [Sauce Demo](https://www.saucedemo.com).  
**Passos:**  
1. Insira o nome de usuário "standard_user".  
2. Insira a senha "secret_sauce".  
3. Clique no botão "Login".  

**Resultado esperado:** O usuário é redirecionado para a página inicial da loja no tempo médio de **2,5 segundos** no desktop e **8,6 segundos** no mobile.

**Status:**  Passou ✅

---

## Ordenação e Filtragem de Produtos

### CT-006: Validar a funcionalidade de ordenação e filtragem de produtos na página inicial
**Descrição:** Validar a funcionalidade de ordenação e filtragem de produtos na página inicial.  
**Pré-condição:** Usuário deve estar logado e visualizando a lista de produtos na página inicial.  
**Passos:**  
1. Acesse a plataforma [Sauce Demo](https://www.saucedemo.com) e faça login com o usuário "standard_user" e senha "secret_sauce".  
2. Na página inicial, localize o dropdown de ordenação no canto superior direito.  
3. Escolha a opção **"Price (low to high)"**.  
4. Verifique se os produtos estão ordenados em ordem crescente de preço.  
5. Escolha a opção **"Price (high to low)"**.  
6. Verifique se os produtos estão ordenados em ordem decrescente de preço.  
7. Escolha a opção **"Name (A to Z)"**.  
8. Verifique se os produtos estão ordenados alfabeticamente.  
9. Escolha a opção **"Name (Z to A)"**.  
10. Verifique se os produtos estão ordenados em ordem alfabética reversa. 

**Resultado esperado:**  
- Os produtos são corretamente ordenados conforme a opção selecionada no dropdown.  
- A interface responde rapidamente às alterações no critério de ordenação.  
- Não há mensagens de erro ou comportamento inesperado.

**Status:**  Passou ✅

---

## Fluxo Completo de Compra (Carrinho -> Finalização)

### CT-007: Fluxo completo de compra
**Descrição:** Validar o fluxo completo de compra, desde a adição de itens ao carrinho até a finalização do pedido.  
**Pré-condição:** Usuário deve estar logado e na página inicial com os produtos disponíveis.  
**Passos:**  
1. Faça login com o usuário "standard_user" e senha "secret_sauce".  
2. Adicione ao menos dois produtos ao carrinho.  
3. Acesse o carrinho e clique em "Checkout".  
4. Preencha o formulário de checkout com dados válidos.  
5. Revise os itens e preços.  
6. Conclua a compra clicando em "Finish". 

**Resultado esperado:**  
- Os itens adicionados ao carrinho devem ser exibidos corretamente.  
- O processo de checkout deve ocorrer sem erros.  
- A compra deve ser concluída com a mensagem **"THANK YOU FOR YOUR ORDER"**.

**Status:**  Passou ✅


---

### CT-008: Fluxo de compra com carrinho vazio
**Descrição:** Validar o comportamento ao tentar realizar o fluxo de compra sem adicionar itens ao carrinho.  
**Pré-condição:** Usuário deve estar logado e na página inicial.  
**Passos:**  
1. Acesse o carrinho sem adicionar itens.  
2. Tente clicar no botão "Checkout".

**Resultado esperado:**  
- O sistema impede a navegação para o fluxo de checkout.  
- Uma mensagem clara informa que é necessário adicionar itens ao carrinho.

**Status:** Falhou ❌

---

## Carrinho de Compras

### CT-009: Adicionar item ao carrinho
**Descrição:** Validar que os produtos podem ser adicionados ao carrinho corretamente.  
**Passos:**  
1. Faça login e adicione um produto ao carrinho.  
2. Verifique se o produto foi adicionado corretamente.

**Resultado esperado:** O produto é exibido corretamente no carrinho com informações completas.

**Status:**  Passou ✅

---

### CT-010: Remover item do carrinho
**Descrição:** Validar que um item pode ser removido do carrinho.  
**Passos:**  
1. Acesse o carrinho e remova um item.

**Resultado esperado:** O item é removido corretamente.

**Status:** Passou ✅

---

### CT-011: Atualizar quantidade de produtos
**Descrição:** Validar atualização da quantidade de produtos no carrinho.  
**Passos:**  
1. Altere a quantidade de um produto no carrinho.  
2. Verifique se o total reflete a mudança.  

**Resultado esperado:** A quantidade e o total são atualizados corretamente.

**Status:**  Falhou ❌

---

## Navegação

### CT-012: Navegar para página de produtos
**Descrição:** Validar navegação para a página de produtos após o login.  

**Resultado esperado:** Página de produtos carregada corretamente com todos os elementos visíveis.

**Status:** Passou ✅

---

### CT-013: Retornar à página de produtos do carrinho
**Descrição:** Validar que o usuário pode retornar à página de produtos.  

**Resultado esperado:** Navegação realizada com sucesso sem erros.

**Status:** Passou ✅

---

## Acessibilidade

### CT-014: Testar contraste de cores
**Descrição:** Validar o contraste de cores da página inicial para garantir a legibilidade.  
**Passos:**  
1. Acesse a página inicial.  
2. Verifique o contraste de cores do texto e do fundo utilizando uma ferramenta de acessibilidade.  

**Resultado esperado:** O contraste de cores atende aos critérios de acessibilidade (WCAG AA ou superior).

**Status:** Falhou ❌


---

### CT-015: Testar navegação por teclado
**Descrição:** Validar se a navegação por teclado está funcionando corretamente.  
**Passos:**  
1. Acesse a página inicial.  
2. Navegue pela página utilizando as teclas Tab, Shift+Tab e Enter.  

**Resultado esperado:** A navegação é fluida e todos os elementos interativos podem ser acessados por teclado.

**Status:** Falhou❌

---

## Responsividade

### CT-016: Testar responsividade em dispositivos móveis
**Descrição:** Validar a responsividade da página inicial em dispositivos móveis.  
**Passos:**  
1. Acesse a página inicial em um dispositivo móvel.  
2. Verifique se todos os elementos (imagens, botões, textos) são responsivos e bem exibidos.  

**Resultado esperado:** Todos os elementos são corretamente ajustados para a tela do dispositivo móvel.

**Status:** Falhou ❌

---

### CT-017: Testar responsividade em diferentes resoluções
**Descrição:** Validar a responsividade da página inicial em diferentes resoluções de tela.  
**Passos:**  
1. Acesse a página inicial em uma tela de resolução 1366x768.  
2. Acesse a página inicial em uma tela de resolução 1920x1080.  

**Resultado esperado:** Todos os elementos são corretamente ajustados para diferentes resoluções de tela.

**Status:** Passou ✅

---

## Usabilidade

### CT-018: Validar clareza das mensagens de erro
**Descrição:** Validar a clareza das mensagens de erro em caso de login falho.  
**Passos:**  
1. Acesse a página de login e insira um nome de usuário e senha incorretos.  

**Resultado esperado:** A mensagem de erro é clara e informativa, orientando o usuário sobre o problema.

**Status:** Falhou ❌



---

## Recomendações de Melhorias de UI

- **Melhoria 1:** Adicionar a função de visualização de senha. 

- **Melhoria 2:** Exibir uma mensagem de confirmação visual (como um checkmark ou pop-up) ao adicionar itens ao carrinho, melhorando o feedback ao usuário.  
- **Melhoria 3:** Adicionar breadcrumbs para facilitar a navegação entre páginas no fluxo de compra.
- 
**Melhoria 4:** Reduzir o número de linhas e manter uma descrição curta e objetiva na descrição dos produtos da PLP



---

## Recomendações de Melhorias Gerais 
- **Melhoria 1:** Desabilitar o botão de login quando os campos E-mail e Senha estiverem vazios, habilitando-o somente após o preenchimento
Logo do Site

- **Melhoria 2:** Permitir o redirecionamento para a home ao clicar na logo

- **Melhoria 3:** Adicionar uma área de inscrição para newsletter

- **Melhoria 4:** Implementar sistema de avaliação para aumentar a confiança do cliente

- **Melhoria 5:** Adicionar um campo de busca no header

- **Melhoria 6:** Adicionar uma área de "Minha Conta"

- **Melhoria 7:** Adicionar opção para alternar entre visualização de lista e grid na PLP.

---


## Recomendações de Automação de Testes

- **Recomendação 1:** Automatizar o fluxo de login com diferentes tipos de usuários (válidos e inválidos) para garantir a cobertura em diferentes cenários. 

- **Recomendação 2:** Criar testes automatizados para validação da ordenação e filtragem de produtos, incluindo diferentes critérios (preço e nome).  

- **Recomendação 3:** Implementar automação para o fluxo completo de compra, simulando a adição de itens ao carrinho e finalização de pedidos. 

- **Recomendação 4:** Automatizar testes de regressão para verificar o fluxos de usuários e identificar possíveis quebras após alterações no código.  







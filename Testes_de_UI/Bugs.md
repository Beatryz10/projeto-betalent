## Bugs Identificados

### Bugs de teste exploratório

- **Botão de Cadastro**

1 - O botão para criar uma nova conta não está disponível na tela de login.

- **Checkout: Your Information**

2 - É possível inserir números em campos destinados a texto.

3 - É possível inserir letras em campos numéricos.

- **Métodos de Pagamento**

4 - Não é possível alterar os dados de pagamento no checkout.

- **Tela de Login**

5 - A mensagem de erro exibida ao digitar um usuário ou senha inválidos está quebrada (layout desalinhado).

---

### Bugs de teste de regressão

- **Atualização de Quantidade** (CT-011)

6 - A funcionalidade de atualização de quantidade não existe na PLP (Página de listagem de produtos).

7 - Também não existe no Mini Cart.

---

- **Botão de Checkout no Carrinho** (CT-008)

8 - O botão "Seguir para o Checkout" aparece mesmo quando não há produtos no carrinho.

9 - É possível finalizar a compra sem adicionar produtos ao carrinho.

---

- **Acessibilidade** (CT-014 e CT-015)

10 - Os elementos em foco não são destacados para usuários que utilizam tecnologias assistivas.

11 - Alguns botões não possuem textos discerníveis para leitores de tela.

---

- **Usabilidade** (CT-018)

12 - A mensagem de erro no login não informa claramente que é necessário utilizar um dos usuários cadastrados previamente para acessar a loja.

---

- **Responsividade** (CT-016)

13 - Em dispositivos móveis, as imagens dos produtos ficam quebradas.

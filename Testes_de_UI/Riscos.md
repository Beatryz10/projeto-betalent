#### **1. Identificação de Riscos**

---

### **Funcionalidade**

- **Login e Autenticação**:
  - Falhas na validação de credenciais (usuários bloqueados, senhas incorretas, etc.).
  - Mensagens de erro pouco claras ou faltantes.
  - Ausência de limite para tentativas de login, permitindo ataques de força bruta.

- **Carrinho de Compras**:
  - Erros ao adicionar/remover itens.
  - Quantidade de itens não atualizando corretamente.
  - Possibilidade de finalizar compras com carrinho vazio.

- **Checkout**:
  - Dados incorretos aceitos nos campos (ex.: letras em campos numéricos).
  - Falta de integração ou indisponibilidade de métodos de pagamento.
  - Erros na validação de endereços ou outros dados do usuário.

---

### **Usabilidade**

- Mensagens de erro pouco claras, prejudicando a experiência do usuário.
- Layouts desorganizados ou inconsistentes, especialmente em dispositivos móveis.
- Falta de feedback visual para ações importantes (ex.: adicionar ao carrinho, aplicar filtros).
- Problemas de acessibilidade (ex.: falta de textos alternativos, navegação por teclado limitada).

---

### **Desempenho**

- Lentidão ao carregar o catálogo de produtos ou aplicar filtros.

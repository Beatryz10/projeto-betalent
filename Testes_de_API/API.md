# Documentação de Testes da API Restful-Booker

## 2.3.2.1 Lista de Cenários Testados

### **Autenticação**
1. Gerar Token de Autenticação:
   - Método: `POST /auth`
   - Resultado: Retorna um token válido em caso de sucesso.

2. Gerar Token com Credenciais Inválidas:
   - Método: `POST /auth`
   - Resultado: Retorna erro 403 Forbidden ao usar credenciais inválidas.

### **Gestão de Reservas**
3. Criar Nova Reserva:
   - Método: `POST /booking`
   - Resultado: Reserva criada com ID único, validação de campos obrigatórios.

4. Buscar Reserva Específica:
   - Método: `GET /booking/:id`
   - Resultado: Retorna os detalhes da reserva se o ID for válido.

5. Listar Todas as Reservas:
   - Método: `GET /booking`
   - Resultado: Retorna uma lista de todas as reservas.

6. Atualizar uma Reserva Existente:
   - Método: `PUT /booking/:id`
   - Resultado: Atualiza os dados de uma reserva válida.

7. Deletar uma Reserva Existente:
   - Método: `DELETE /booking/:id`
   - Resultado: Retorna status 201 Created ao excluir uma reserva.

### **Filtros e Buscas**
8. Buscar Reservas por Nome:
   - Método: `GET /booking?firstname=:firstname&lastname=:lastname`
   - Resultado: Retorna reservas com o nome correspondente.

9. Buscar Reservas por Check-in Date:
   - Método: `GET /booking?checkin=:date`
   - Resultado: Retorna reservas que iniciam no check-in especificado.

10. Buscar Reservas por Check-out Date:
    - Método: `GET /booking?checkout=:date`
    - Resultado: Retorna reservas que terminam no check-out especificado.

---

## 2.3.2.2 Resultados Obtidos

### **Autenticação**
- Sucesso ao gerar token com credenciais válidas.
- Validação apropriada para credenciais inválidas (403 Forbidden).

### **Gestão de Reservas**
- Criação de reserva validada para todos os campos obrigatórios.
- Atualização e exclusão funcionaram conforme esperado.
- Listagem e busca por ID retornaram dados corretos.

### **Filtros e Buscas**
- Filtragem por nome, check-in e check-out funcionaram com parâmetros válidos.

---

## 2.3.2.3 Bugs Encontrados
1. **Erro na Exclusão de Reserva**:
   - O código de resposta HTTP para exclusão (`DELETE /booking/:id`) está inconsistente, retornando 201 Created em vez de 204 No Content.

2. **Mensagem de Erro Genérica**:
   - Ao buscar uma reserva com um ID inexistente, a API retorna um erro genérico. Melhor seria um código 404 Not Found com uma mensagem específica.

---

## 2.4 Pontos de Atenção

- **Tratamento de Erros**: Validação apropriada foi testada, mas erros genéricos precisam ser refinados.
- **Validação de Campos Obrigatórios**: Os testes confirmaram que campos ausentes geram erros.
- **Formato das Datas**: Validado para o padrão `YYYY-MM-DD`.
- **Códigos de Resposta HTTP**: Pequenas inconsistências foram observadas e sinalizadas.

---

## Premissas
1. Dados de exemplo fornecidos na documentação foram usados como base.
2. As reservas foram criadas e deletadas para validar todos os endpoints.

  

---

### **Desafio Técnico: Gerenciamento de Pedidos e Estoque**
#### **Contexto**  
Você foi contratado para desenvolver um pequeno sistema de pedidos para uma loja. O sistema deve permitir criar pedidos de clientes, vinculando produtos ao pedido e atualizando o estoque automaticamente.  

---

### **Requisitos**
1. **Modelagem de Banco de Dados**  
   - Crie um banco de dados com as tabelas:  
     - `customers (id, name, email)`  
     - `products (id, name, price, stock_quantity)`  
     - `orders (id, customer_id, total_price, created_at)`  
     - `order_items (id, order_id, product_id, quantity, price)`  

2. **Regras de Negócio**
   - Ao criar um pedido, o sistema deve:  
     - Associar o pedido a um cliente.  
     - Calcular o total com base nos produtos e suas quantidades.  
     - Atualizar a quantidade do estoque dos produtos.  
     - **Não permitir pedidos caso o estoque não seja suficiente.**  

3. **Desenvolvimento no Laravel**
   - Criar **Models** e **Migrations** para as tabelas.  
   - Implementar um **Service** ou **Repository** para processar a criação de pedidos, respeitando o princípio da **Responsabilidade Única (SRP - SOLID)**.  
   - Criar uma **rota API (`POST /orders`)** para registrar um novo pedido, recebendo o **customer_id** e uma lista de produtos com quantidades.  

---

### **Exemplo de Entrada na API (`POST /orders`)**
```json
{
  "customer_id": 1,
  "products": [
    { "product_id": 2, "quantity": 3 },
    { "product_id": 5, "quantity": 1 }
  ]
}
```

### **Exemplo de Resposta Esperada**
```json
{
  "order_id": 12,
  "total_price": 150.00,
  "status": "success"
}
```

---

### **Critérios de Avaliação**
✅ **Organização do Código** (Uso correto de controllers, services e models).  
✅ **Respeito aos Princípios SOLID**, principalmente **SRP e DIP**.  
✅ **Uso correto do Eloquent para relacionamentos**.  
✅ **Tratamento de erros e validações** (ex: verificar se há estoque suficiente).  

Boa Sorte 🚀

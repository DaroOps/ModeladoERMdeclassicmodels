1. **Obtener todos los productos en stock:**

   ```sql
   select productName, quantityInStock from products;
   ```

2. **Lista de empleados que trabajan en una oficina específica (por ejemplo, '1'):**

   ```sql
   SELECT lastName, firstName, officeCode FROM employees WHERE officeCode = 1;
   ```

3. **Detalles de un cliente específico (por ejemplo, customerNumber = 101):**

   ```sql
   SELECT * FROM customers WHERE customerNumber = 209;
   ```

4. **Listar todos los pagos realizados por un cliente específico (por ejemplo, customerNumber = 101):**

   ```sql
   SELECT * FROM  payments WHERE customerNumber = 209;
   ```

5. **Obtener todos los pedidos con estado 'Shipped':**

   ```sql
   SELECT * FROM orders WHERE status= 'Shipped';
   ```

6. **Cantidad total de productos en stock:**

   ```sql
   SELECT SUM(quantityInStock) FROM products;
   ```

7. **Lista de todos los empleados con su jefe (si tienen):**

   ```sql
   SELECT * FROM employees WHERE reportsTo != 'NULL';
   ```

8. **Detalles de oficinas en un país específico (por ejemplo, 'USA'):**

   ```sql
   SELECT * FROM offices WHERE country = 'USA';
   ```

9. **Listar todos los clientes en una ciudad específica (por ejemplo, 'Madrid'):**

   ```sql
   SELECT * FROM customers WHERE city = 'Madrid';
   ```

10. **Productos con precio de compra mayor a 50:**

    ```sql
    SELECT * FROM products WHERE buyPrice > 50;
    ```

### Consultas Multitabla

1. **Obtener todos los pedidos realizados por un cliente específico (por ejemplo, customerNumber = 101) con detalles del producto:**

   ```sql
   SELECT customerName, customerNumber 
   FROM customers 
   INNER JOIN orders USING (customerNumber) WHERE customerNumber=209;
   ```

2. **Listar todos los empleados junto con la oficina en la que trabajan:**

   ```sql
   SELECT lastName, officeCode FROM employees INNER JOIN  offices USING(officeCode);
   ```

3. **Listar todos los clientes junto con su representante de ventas:**

   ```sql
   SELECT c.customerNumber, c.salesRepEmployeeNumber, e.firstName, e.lastName 
   FROM employees e 
   INNER JOIN customers c 
   ON c.salesRepEmployeeNumber = e.employeeNumber;
   ```

4. **Obtener el nombre y la cantidad total ordenada de cada producto:**

   ```sql
   SELECT p.productCode, d.quantityOrdered 
   FROM products p
   INNER JOIN orderdetails d 
   ON d.productCode = p.productCode;
   
   ```

5. **Listar todas las oficinas y el número de empleados en cada una:**

   ```sql
   SELECT e.employeeNumber, e.firstName, e.lastName, o.officeCode 
   FROM employees e 
   INNER JOIN offices o 
   ON o.officeCode = e.officeCode ;
   ```
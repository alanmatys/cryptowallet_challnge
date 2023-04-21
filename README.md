# cryptowallet_challnge
Crypto wallet (Custodial) Churn model

# Data Challenge

Dentro de las transacciones que puede realizar un usuario, las que generan revenue, son la compra y venta crypto (2%), los swaps (1%) y las compras con tarjeta (5%). 

Para este data challenge buscamos sacar el LTV (lifetime value) de los usuarios. Para esto, primero debemos calcular los siguientes cohortes por fecha de primer transacción: 

- Churn Rate: Numero de personas que hicieron churn, tomando churn como persona que no transaccionó en el ultimo mes, a mes cerrado.
- Retención:  1 - churn.

Y la metrica:

- Average Revenue Per User:
    - Volumen proceasdo (en USD) / total users.
    

Una vez obtenida esta información, el LTV se puede calcular como = ARPU / CHURN. 

Para calcular las métricas, se utilizaran las siguientes tablas en formato csv, donde haciendo click sobre el nombre comenzará la descarga:

**Users:**

- Es una tabla con información sobre el usuario, las columnas son:
    - user_id: el id del usuario
    - gender: genero de la persona
    - birthdate: fecha de nacimiento
    - createdat: fecha de creacion de la cuenta

**Transactions:** 

- Tabla con información sobre las transacciones de los usuarios en la tabla users, columnas:
    - id: id de la transaccion
    - user_id: el id del usuario
    - amount: monto en unidades de la currency de la transaccion
    - state: el estado de la transaccion
    - operation_type: si es un debito o credito de cara al usuario
    - transaction_type: tipo de transaccion
    - currency: moneda en la que fue hecha la transaccion
    - createdat: momento en que fue hecha la transaccion

**Rates:**

- Tabla con información sobre los tipo de cambios que hay entre monedas. Sirve para pasar las unidades a dólares, columnas:
    - base_currency: moneda que se vende
    - quote_currency: moneda que se compra
    - price: es el ratio entre la base_currency y la quote_currency

### Consideraciones

- Se espera que el candidato realice el análisis de los datos, cohortes y métricas en un script de Spark y SQL.
- La presentación de la respuesta al challenge puede ser hecha de la forma en que prefiera el candidato.
- El / Los scripts utilizados deberán ser publicados en algún repositorio.
- Toda la info en este challenge no es real.
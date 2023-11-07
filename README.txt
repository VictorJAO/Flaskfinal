AGREGAR PERSONA
curl --location 'http://localhost:5000/personas' \
--header 'Content-Type: application/json' \
--data-raw '{
"nombre": "Pepe",
"apellido": "Alfonso",
"email": "ppaln@example.com",
"dni": "28652478"
}
'

LISTAR PERSONA
curl --location 'http://localhost:5000/personas' \
--data ''

BUSCAR PERSONA
curl --location 'http://localhost:5000/personas/buscar' \
--header 'Content-Type: application/json' \
--data '{
"dni": "12345678"
}
'

MODIFICAR PERSONA
curl --location --request PUT 'http://localhost:5000/personas' \
--header 'Content-Type: application/json' \
--data-raw '{
"dni": "12345678",
"nombre": "Jose",
"apellido": "Pérez",
"email": "nuevo_email@example.com"
}'

ELIMINAR PERSONA
curl --location --request DELETE 'http://localhost:5000/personas/28652478' \
--header 'Content-Type: application/json' \
--data '{
"dni": "28652478"
}
'

Base de datos y postman:
1. Abrimos XAMPP para conectar el puerto.
2. Abrimos DBeaver para generar la base de datos con nombre persona, y una tabla con el nombre persona. 
3. Dentro de la tabla generamos una columna "id" que luego de hacerla generamos el constraint.
4. Añadimos el resto de las columnas y una vez que fue creada y el script py lo ejecuta pasamos a postman.
5. En postman generamos una collection que tenga los metodos POST (para agregar y buscar), GET (para listar), PUT (para modificar), DEL (para eliminar).

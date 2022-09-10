# Fast API
API: interfaz para interactuar con un sistema
Rest API: Restricciones de una API. Estilo arquitectónico.

Framework de python que permite construir web API's de manera rápida y eficiente.

+ Utiliza Starlette para resolver la capa web y Pydantic para la manipulación de datos.
+ Soporta: websockets, GraphQL, SQL y NO SQL, ect.
+ Valida automáticamente los tipos de entrada y salida de los métodos.

Hello World: (archivo main)
```python
from fastapi import FastAPI
app_name = FastAPI()

@app.get("/")
async def root():
	return {"message": "Hello World"}
```

¿Cómo usar?
```bash
$ unicorn main:app_name --reload
```

luego:
```bash
$ curl -X GET "linkskdjfsk" -H "accept: application/json" -w "\n" -i
```

Representational state transfer
+ Cliente-servidor: Lógica de interfaces y la lógica de la aplicación debería estar separada.
+ Sin estado
+ Sistema construido por capas

## Componentes
+ Endpoint: Donde se recibe una llamada **API**.
+ Método:
 
|Método | Descripción |
| - | - |
| Get | Obtener recurso(s) del servidor |
| Post | Crear un recurso nuevo |
| Patch/Put | Modificar o editar un recurso existente. Patch modifica solo un atributo, put todos |
| Delete | Borra un recurso del servidor. |
+ Cabecera
+ Body

## Path Parameters
```Python
@app.get("users/{user_id}")
async def users(user_id: int): # fast API hace la validación del tipo.
	return get_user_by_id(user_id=user_id)

```
Se pueden utilizar tipos enumerados.

Hay que ser cuidadosos en el orden. 

## Error handling
Solo hay que definir semántica de excepciones.

## Query parameters
```python
@app.get("/users/") # esto aparece en <url>/users/
async def get_user_list(
	user_from: Optional[int] = 0,
	user_to: Optional[int] = None
):
	return USERS[user_from:user_to]
```

Si no tienen valor por defect , entonces los parámetros son requeridos.

## Request Body
Para request complejas que envían datos al servido.Necesitamos un modelo para validar la estructura de los datos requeridos para un usuario.

```python
from pydantic import BaseModel, EmailStr
class UserIn(BaseModel):
	name: str
	surname: str
	age: Optional[int] = None # No es requerido
	mail: EmailStr # Provista por pydantic. Valida que sea un mail
	active: bool
```

```python
class UserOut (BaseModel):
	id: int
	name: str
	operation_result: int

app.post("/ussers/") # end point del post
async def create_user(new_user: UserIn) -> UserOut:
	new_id = len(USERS) + 1
	...
	return UserOut(id= new_id
		name=name
		operation_result=res
	)
```

## Testing
`TestClient`: se pueden escribir casos de prueba usando `pytest`.

```python
from fastapi.testclient import TestClient
from fastapi import status

from main import app

client = TestClient(app)

def test_get_single_user():
	respinse = client.get("/users/4")
	assert ...
	...
	
```
Correr los test:  
```bash
$ py.test .s test_users.py --disable-warnings
```

## Documentación
+ Docsrting

+ Estándar `Swagger` o `ReDoc`  
	+ FastAPI genera documentación (Swagger o redoc) automáticamente.
	+ Usar `/doc` o `/redoc`

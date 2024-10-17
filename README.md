# FastFoodAPI-Explorer

**FastFoodAPI-Explorer** é uma aplicação simples para explorar os dados de restaurantes e seus respectivos cardápios através de uma API pública. Este projeto foi desenvolvido como parte de um curso da Alura e oferece uma maneira fácil de acessar e salvar dados sobre restaurantes e cardápios em arquivos JSON, além de fornecer endpoints via FastAPI.

## Funcionalidades

- Consulta de uma lista de restaurantes e seus cardápios a partir de uma API pública.
- Salvamento de cardápios de restaurantes específicos em arquivos JSON.
- API com endpoints para consultar dados dos restaurantes.

## Tecnologias Utilizadas

- **Python**: Para manipulação de requisições HTTP e processamento de dados.
- **FastAPI**: Framework utilizado para criar os endpoints da API.
- **Requests**: Biblioteca para fazer requisições HTTP.
- **JSON**: Para manipulação e armazenamento de dados no formato JSON.

## Instalação

1. Clone este repositório:
   ```
   git clone https://github.com/guidxs/fastfoodapi-explorer.git
   ```
2. Navegue até o diretório do projeto:
   ```
   cd fastfoodapi-explorer
   ```
3. Instale as dependências:
   ```
   pip install -r requirements.txt
   ```
## Como Usar

**1. Salvando cardápios em arquivos JSON**

No arquivo `app.py`, os dados dos restaurantes são buscados da API pública e salvos localmente em arquivos JSON.

Execute o arquivo `app.py`:
```
python app.py
```

Se a requisição for bem-sucedida, arquivos JSON serão criados no diretório de execução, com o nome de cada restaurante. Cada arquivo conterá uma lista de itens do cardápio, com preço e descrição.

**2. Explorando dados via API**

O arquivo `main.py` utiliza o FastAPI para disponibilizar endpoints que permitem a consulta dos dados dos restaurantes. Os endpoints disponíveis são:
- `/api/hello`: Retorna um JSON com a mensagem "Hello World".
- `/api/restaurantes/`: Retorna a lista completa dos restaurantes. Você pode também filtrar pelo nome do restaurante para obter seu cardápio específico.

## Exemplo de uso:

1. Execute o servidor FastAPI:
```
uvicorn main:app --reload
```

2. Acesse o endpoint para visualizar os dados:
  - **Lista todos restaurantes:**
```
GET http://127.0.0.1:8000/api/restaurantes/
```
  - **Filtrar por restaurante específico (por exemplo, "McDonald's"):**
```
GET http://127.0.0.1:8000/api/restaurantes/?restaurante=McDonald's
```

## Exemplo de retorno

- Retorno para todos os restaurantes:
```
{
  "Dados": [
    {
      "Company": "McDonald's",
      "Item": "Big Mac",
      "price": "45.34",
      "description": "Molhos deliciosos para realçar seus pratos."
    },
    ...
  ]
}
```
- Retorno para um restaurante específico: 
```
{
  "Restaurante": "McDonald's",
  "Cardapio": [
    {
      "item": "Big Mac",
      "price": "45.34",
      "description": "Molhos deliciosos para realçar seus pratos."
    },
    ...
  ]
}
```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

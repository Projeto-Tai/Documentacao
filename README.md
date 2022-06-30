
 ## Processo da implementação do projeto TAI
  
  

- [] Criar a Camada Model, repository, controler, service das Tabela Categoria,Produto,User,UserLogin, Comerciante e doação.
- [] Criar Camada de Security,BasicSecurityConfig, UserDetailsServiceImpl, UserDetailsServiceImpl.
- [x] Criar as camadas controller e repository teste JUnit.
- [x] Configurar os application.properties e adicionado as applications Dev.properties e prod.properties na pasta src/main/resources para o deploy no heroku.
- [x] Criar a camada swaggerConfiguration para o deploy no heroku. 
- [x] Executar os testes no Insomnia tanto em Dev como em Prod.             

 
 


<br>
<h3 align="center">
DER: Modelo de Entidade-Relacionamento :
  
```mermaid
classDiagram
class Categoria{
  - id : Long
  - nome : VARCHAR(255)
  - tipo: BOOLEAN
  - foto: VARCHAR(255)
  - produto : List ~Produto~
  + getAll()
  + getById(Long id)
  + getBytipo(Boolean tipo)
  + postCategoria(Categoria categoria)
  + putCategoria(Categoria categoria)
  + deleteCategoria(Long id)
}
class Produto {
  - id : Long
  - nome : VARCHAR(255)
  - quantidade: INT
  - descrição: VARCHAR(500)
  - preco : INT
  - foto :VARCHAR(255)
  - peso : DECIMAL
  - perecivel: BOOLEAN
  - ativo: BOOLEAN
  - dataFabricacao:VARCHAR(255)
  - dataValidade:VARCHAR(255)
  + getAll()
  + getById(Long id)
  + getBynome(String nome)
  + getByDataIntervalo (String inicio, String fim)
  + postProduto(Produto produto)
  + postProduto(Produto produto)
  + deleteCategoria(Long id)
}
class User {
  - id : Long
  - nome : VARCHAR(255)
  - usuario :  VARCHAR(255)
  - senha :  VARCHAR(255)
  - foto :  VARCHAR(255)
  - tipo : VARCHAR(255)
  - senha :VARCHAR(255)
  - cep: VARCHAR(255)
  - produto : List ~Produto~
  + getAll()
  + getById(Long id)
  + autenticarUser(UserLogin userLogin)
  + cadastrarUser(User user)
  + atualizarUser(User User)
}
class UserLogin{
 - id : Long
  - nome : VARCHAR(255)
  - usuario :  VARCHAR(255)
  - senha :  VARCHAR(255)
  - foto :  VARCHAR(255)
  - tipo : VARCHAR(255)
  - senha :VARCHAR(255)
  - cep: VARCHAR(255)
}
Categoria --> Produto
User --> Produto
```  

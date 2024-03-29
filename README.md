# Identity Server - Introdução

### Resumo: 

Um servidor IdentityServer que serve para implementar o protócolo Oauth2 e a camada OpenId Connect no .NET! O programa irá escopar dois principais métodos: GetProfileDataAsync e IsActiveAsync que estão na classe ProfileService.
Basicamente, a classe irá receber um contexto que possui um usuário, irá receber as claims (informações) desse usuário e irá adicionar em uma lista de claims. Elas serão usadas para definir as regras que serão aplicadas para aquele
usuário específico. Em seguida, será validado se o usuário está ativo ou não. 

O servidor também é responsável por definir as regras que definem o que é um usuário. Atualmente foi definido o conceito de usuário do sistema e o próprio sistema também está incluso tento em vista que o servidor atual irá receber uma requisição
do client que será o frontend da aplicação. 

### Configuration: Classe IdentityConfigurarion

- Concentra as configurações relacionadas à identidade e à autorização no contexto de algum sistema ou aplicação.
- Define os recursos de identidade disponíveis na aplicação.
- Define os escopos de API que podem ser acessados pelos clientes.
- Define os clientes (aplicações ou serviços) que podem acessar a API e seus níveis de acesso.

### Initializer: Classe DBInitializer e Interface

- Esta classe é responsável por inicializar a base de dados da aplicação criando papéis (roles) e usuários padrão.
- O construtor recebe instâncias de MySQLContext, UserManager e RoleManager por meio da injeção de dependência e as armazena nas propriedades privadas correspondentes.
- Este código cria usuários e papéis iniciais para fins de demonstração ou configuração inicial. Em uma aplicação real, o cadastro de usuários normalmente seria feito por uma interface separada.

### MainModule: Controllers 

Basicamente, são todos os controllers utilizados na aplicação. 

- AccountController: Este exemplo de controlador faz um sistema comum de login/logout/cadastro para contas locais e externas.
O serviço de login cuida das informações dos usuários, mas só mantém essas informações temporariamente na memória e não é adequado para uso real.
O serviço de interação permite que a interface do usuário se conecte ao IdentityServer para verificar e obter informações.

- ConsentController: Este controlador lida com a interface de consentimento.

- GrantsController: Este controlador de exemplo permite que um usuário revogue permissões concedidas a clientes.





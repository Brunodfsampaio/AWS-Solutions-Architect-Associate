### Neste lab, vamos criar um user com permissão full access. A ideia é não usar a conta root para novos labs. 
- se você não tive um MFA ativo na sua conta root, é ideal ativar. assim como, na conta do novo usuário que será criada.
- após criar o novo usuários, vamos usar o Sign-in URL for IAM users para acessar o serviço
- também vai ser criado access key e uma secret key.
- tudo isso deverá ser salvo
![image](https://github.com/user-attachments/assets/cf38b730-03c4-450f-bb5e-52d659040ec7)

#### Passo 1 - Account Alias
- aqui vamos criar o usuário
- Account alias > create
- escolha uma nove e faça a criação.
- se voce copiar o url e colar, ele vai reconhecer o que foi criado e vai pedir IAM user e senha e automaticamente vai desconectar da sua conta logada.

#### Passo 2 - User
- agora definitavemente criar o usuário
![image](https://github.com/user-attachments/assets/3a8072a6-afdc-4e00-90dd-201aff21f73d)

- user > create user

![image](https://github.com/user-attachments/assets/b5b75e43-d8dc-400b-908b-144bcd295270)

- aqui vamos dar um nome para o user, não vou especificar o user no identity center, apenas iam user.
- em seguida, eu vou definir uma senha (não quero a opção para gerar automático)

![image](https://github.com/user-attachments/assets/7515e48f-2085-4f30-a3d7-664d14200762)

- e não quero que a senha seja redefinida quando eu realizar o primeiro loggin.
- next

![image](https://github.com/user-attachments/assets/37f66f15-4264-4805-acf4-bf477661b7e6)

- Aqui vamos pode 'atachar' o usuário à um grupo, copiar permissões ou políticas
- vou criar um grupo ADM.
- create group

![image](https://github.com/user-attachments/assets/b6c7293f-3d94-4f19-bbf3-a655ab69fc18)

- aqui vou dar um nome ao grupo e selecionar a política de acesso de administrador
- após > create group

![image](https://github.com/user-attachments/assets/413026ba-2e23-4276-93f9-751bede4b928)

- irei selecionar o grupo que criei e dar next.

![image](https://github.com/user-attachments/assets/59bc7cf2-0cef-44a2-a042-c2c88b35366a)

- não irei definir tags.

![image](https://github.com/user-attachments/assets/810b525f-8965-4d8d-ae98-979772669220)

- após, será criado o novo usuário.
- aqui vamos copiar a url de login, username e o password para acessar a aws a partir de agora.
- podemos também realizar o download .CSV para salvar em local seguro E enviar as instruções via e-mail.

![image](https://github.com/user-attachments/assets/07332063-ecf0-4034-b512-82570c963923)

- após isso, voltamos para user e vamos habilitar um MFA para esse novo usuário.

![image](https://github.com/user-attachments/assets/78be7666-0129-4f75-a598-3769c082810a)

- aqui eu vou escolher o app de autenticação.

![image](https://github.com/user-attachments/assets/55f553d4-5a65-4896-a7a3-04a76228debc)

- após isso, vamos no account setting > edit para visualizar as políticas

![image](https://github.com/user-attachments/assets/c7f84aab-eb4f-4aaa-aabd-548a7705b78f)

- nesse caso, irei desabilitar apenas o tempo que o password vai expirar. após "save changes"

#### Passo 3 - logar com o user iam criado
- vamos em Users > Security Credentials e vamos copiar o link da console

![image](https://github.com/user-attachments/assets/e3554787-eb9f-43b1-9d0c-9c390e5c4e5a)

- após isso, você será deslogado da sua conta atual e vai logar na conta iam.

> stay focused.

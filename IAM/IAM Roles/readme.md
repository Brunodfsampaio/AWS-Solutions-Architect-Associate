### Este é um lab mostrando como criar um role e depois 'attachar' ela à uma instância.


#### Passo 1 - localizar a opção Role dentro do IAM
- depois iremos em Create Role
![image](https://github.com/user-attachments/assets/9ad57ced-bcc1-435e-bb6d-4782ab0f5e64)

- no meu caso, irei escolher a opção dos serviços da AWS, onde vai permitir um serviço interagir com outro serviço.
- no caso da AWS account, é como se você fosse permitir uma conta de terceiro para interação
- identidade web, é onde envolve algo como Cognito para reconhecimento
- e por fim, uma  SAM federation ou política customizada.

![image](https://github.com/user-attachments/assets/fd164a9d-9a26-4cc1-a48a-4c8c57c87e4e)

- next

![image](https://github.com/user-attachments/assets/01a97df2-8ff2-4c2e-820c-dce35419cb0a)

- aqui você vai ver uma lista de roles criadas pela AWS.
- nesse lab, vou atribuir uma role de Administrator Access.
- next

![image](https://github.com/user-attachments/assets/4ba66c4e-d528-4e5a-8c37-6c37ec92efc1)

- aqui iremos dar um nome para a role e ver o json dela.
- create role.

![image](https://github.com/user-attachments/assets/c33d9601-5333-4ed9-8986-4648c9e0984b)

- durante a criação de uma instância, já podemos attachar a role nela.

![image](https://github.com/user-attachments/assets/dcc78165-02a2-4f74-8ff3-805ac90ad221)

> stay focused.





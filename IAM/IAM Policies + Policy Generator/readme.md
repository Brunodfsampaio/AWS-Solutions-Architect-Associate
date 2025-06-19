![image](https://github.com/user-attachments/assets/4ef46cf8-a0af-4a41-b544-c37f52625028)### Criando Políticas personalizadas no IAM Policies

#### Vale lembrar que...
- Role (função) é quem assume as permissões — uma identidade temporária usada por serviços ou usuários para executar ações.
- Policy (política) é o que pode ser feito — o conjunto de regras e permissões que controlam acesso a recursos da AWS.

#### Passo 1 - localizar a opção na console
- vamos localizar e acessar as Policies

![image](https://github.com/user-attachments/assets/57700e36-20e0-43eb-bcd4-7fcae7b28051)

- aqui vamos ver várias policies já configuradas pela AWS.

#### Passo 2 - Create Policy
- acessar > Create Policy

![image](https://github.com/user-attachments/assets/1c049946-c9be-485d-aa26-130f415abe0a)

- nessa etapa podemos escolher em criar a policy no modo Visual ou JSON.
- irei criar primeiramente no modo Visual, depois mostrarei o JSON generator.
- ao escolher o serviço (no caso eu escolhi S3), vai aparecer várias opções de interação com este.

![image](https://github.com/user-attachments/assets/07365025-e3e4-4bde-a31f-6b3d7c6dfaff)
![image](https://github.com/user-attachments/assets/9fa670d9-97f5-4c96-87a5-b9e50fb61d95)

- no caso, será habilitado as opções de acordo com a necessidade de uso do usuário/serviço.

![image](https://github.com/user-attachments/assets/65e4b018-aae4-468c-ade4-5d49b565685f)

- aqui podemos especificar um bucket específico ou deixar no modo completo.

![image](https://github.com/user-attachments/assets/02bdf9b4-e14f-4452-b578-88923a0eeec6)

- e ainda adicionar IP específico ou MFA para usuário

![image](https://github.com/user-attachments/assets/6f00d4b4-60eb-4676-9ca4-088490838fa2)

- na etapa seguinte vamos dar um nome para essa nova política

![image](https://github.com/user-attachments/assets/30e573cb-a0e3-402c-9118-1a9892683d94)

- create policy !
- após isso, para usar essa política criada, podemos atribui ela em uma role ou user (ou grupo).

#### Passo 2 - JSON generator
- acessar: https://awspolicygen.s3.amazonaws.com/policygen.html

![image](https://github.com/user-attachments/assets/854f1dd9-61db-4bbd-99b1-40b958861417)

![image](https://github.com/user-attachments/assets/a3437939-2c90-459e-8aa1-cf90f9eb1fef)

- no exemplo eu estou criando um JSON para criação, listar e deletar buckets.
- em ARN, podemos copiar o arn de um user, por exemplo.

![image](https://github.com/user-attachments/assets/93368a07-1ce5-43ca-94cc-53ee3f11428a)

- clicando em 'add statement' vai ser gerado a exibição das políticas e depois 'generate'

![image](https://github.com/user-attachments/assets/f464a80d-b9c0-4a0d-8e13-58ac39b0efe3)

- vamos copiar essa policy em formato JSON, voltaremos para as policies no IAM, criaremos uma nova política e na escolha entre visual ou JSON, escolheremos a segunda opção e colaremos a policy gerada

![image](https://github.com/user-attachments/assets/c098d494-8db8-4b58-bc00-d9f3779914f2)
![image](https://github.com/user-attachments/assets/c1be8934-7dee-4c47-a11f-54b569547773)

> stay focused !







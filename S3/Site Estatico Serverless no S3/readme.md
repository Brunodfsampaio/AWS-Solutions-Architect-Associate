### Neste lab, não vamos criar uma EC2 com ebs e index.html. Aqui vamos baixar o conteúdo de um site estático e fazer upload dele completo diretamente no bucket.
- por ser um site estático (sem processamento) pode ser utilizado até para um currículo online, já que a AWS nos fornece 5GB free.

- ...vamos lá!

#### Passo 1 
- procurei um site para baixar um template pronto. Infelizmente o site "freecss"(bastante conhecido) está down, então eu baixei o modelo do site "templatemo".

#### Passo 2
- criar um bucket e fazer upload da pasta.
![image](https://github.com/user-attachments/assets/262f0948-d232-43e5-8cec-8964c72aac13)
![image](https://github.com/user-attachments/assets/9eb20f60-8ac6-4e91-add9-19cc5a082fb8)
- vamos selecionar "adicionar pasta" já que o arquivo baixado do site é um .zip com uma pasta e seus respectivos objetos.
![image](https://github.com/user-attachments/assets/9303bf56-fd13-4e56-8b0f-82008c284a8f)
![image](https://github.com/user-attachments/assets/9dfde2a1-f606-415f-acfc-d1cb0edf77b7)
- nesse caso eu não precisarei habilitar versionamento de arquivo, pois não irei mudar as configurações
![image](https://github.com/user-attachments/assets/d3ae4770-f0d3-4613-8efb-361bc0c8f3a1)
- nas permissões é bem importante habilidar permissões individuais da ACL e em "TODOS (ACESSO PÚBLICO), habilitar as leituras.
![image](https://github.com/user-attachments/assets/9c361d27-72ab-4a5d-b3fd-5133be6396fe)
- aqui vamos permanecer com a classe standart de storage...
![image](https://github.com/user-attachments/assets/7f4421ca-a199-4041-9743-eacbf5adf06e)
- não irei alterar cripto, função de soma e nem adicionar tags...
![image](https://github.com/user-attachments/assets/9d24896b-d929-4de7-a924-30aa15db88fe)
- depois é só fazer o upload!

#### Passo 3
- dizer para o bucket S3 que ele vai 'hostear' o site estático.
- selecione o bucket > propriedades > hospedagem de site estático
![image](https://github.com/user-attachments/assets/a6744c72-09ff-4d6b-9de4-603b1448b53e)
![image](https://github.com/user-attachments/assets/6efa5178-97f4-4536-83cb-93df565d8ce8)
- é só clicar em editar para acessar as configurações....
- vamos ativar a hospedagem;
- por fim, dar um 'save changes'
![image](https://github.com/user-attachments/assets/dde7c9b3-97ea-44aa-8bf4-c788c6472321)
![image](https://github.com/user-attachments/assets/5c79ba19-b9f1-462d-97c9-7ecd40aa33ee)

- a url do site já vai estar diponível:
![image](https://github.com/user-attachments/assets/fd1cc67f-684d-48fc-a3f6-00eda639fb87)

#### porém....
![image](https://github.com/user-attachments/assets/d3c0023c-695b-4412-a959-eadc0e6a708b)
- ao copiar a url e colar, apareceu o erro 403.


#### Passo 4 - resolvendo o b.o
- Voltaremos ao bucket, selecionar o objeto (pasta) > ir em Ações e depois "tornar público usando ACL"
![image](https://github.com/user-attachments/assets/5f693475-3beb-4d7e-a981-07476bf8d912)
> tornar público.

#### Passo 5 - entrar na pasta, verificar se o index.html está público e com as regras de leitura ativada. Após isso é só copiar a url dele e tentar novamente.
![image](https://github.com/user-attachments/assets/fd363f8b-feae-4ba2-8028-4c7e2d7842fa)

stau focused!!!










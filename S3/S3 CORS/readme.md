### Lab rápido mostrando como habilitar o CORS no S3.
- se você não sabe ou não lembra o que essa feature faz, vai lá no mapa mental que eu descrevi ela...
---

### Passo 1 - localizando...
- basta entrar no bucket > permissões > cors > editar
![image](https://github.com/user-attachments/assets/a04c8539-47d1-45a2-bbe3-951ee08265e9)

![image](https://github.com/user-attachments/assets/6877f545-d95f-4167-82e8-8aef9fb3c60a)

###O campo AllowedOrigins define quais origens (ou seja, quais domínios ou sites) são permitidos a realizar requisições Cross-Origin (CORS) no seu bucket S3.

-depois é só salvar!

### em resumo, quando uma página for chamada e está tiver algum arquivo dentro do bucket s3, o domínio vai chamar o s3 e o bucket vai permitir o origin vindo do domínio porta 80, protocolo TCP para liberar o acesso.

Stay focused.

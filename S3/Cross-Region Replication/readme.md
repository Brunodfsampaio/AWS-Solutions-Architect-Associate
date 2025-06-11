### Neste lab, não irei efetivar a replicação pois essa feature gera encargos... porém irei demonstrar como é o passo a passo.

#### Passo 1 
- para o cross ser habilitado, é necessário o versionamento estar também.
![image](https://github.com/user-attachments/assets/e4ad9593-8639-4942-8214-2c8c97ebae8c)

- lembrando que depois que ele é criado, não pode ser excluído, apenas suspenso.
- vou usar meu bucket já criado em us-east 1 e criar um novo em Ohio.
![image](https://github.com/user-attachments/assets/d023ea1a-36ca-43f9-a76f-cbfe233e011e)
![image](https://github.com/user-attachments/assets/c2711753-a0e9-4825-8be1-bf72c3525c4e)

-depois irei no meu bucket principal > gerenciamento > regras de replicação > criar regra de replicação
![image](https://github.com/user-attachments/assets/fcc0d9a7-18a5-4e34-ab2b-483074f8556f)
- dei um nome;
- status já irei deixar habilitado;
- no bucket de origem, vou deixar aplicado para todos os objetos do bucket.

![image](https://github.com/user-attachments/assets/c114ac82-dd1b-4994-885e-2a3ddcecba4f)
-escolhi o bucket existente.
![image](https://github.com/user-attachments/assets/dd1b6206-a343-40c5-9126-faedb989894f)
- como comentei, para o cross ser ativado, é necessário o versionamento. no caso eu criei o novo bucket sem ele, terei que habilitar..
![image](https://github.com/user-attachments/assets/b285c3cf-eb6c-4bc2-8f63-91d0d91cc2a7)

- em função já pode ser definidos roles para uso do bucket/objetos
- pode ser habilitado a cripto com KMS (pago)

![image](https://github.com/user-attachments/assets/ebcb1443-8b7d-470d-84cb-6c14fb7dc659)
- podemos alterar a classe de armazenamento do bucket.

![image](https://github.com/user-attachments/assets/aee425b4-3aa7-4e28-86b3-1717afeeb721)
- na primeira opção as replicações serão em média de 15minutos; ($$$)
- na segunda, o usuário recebe métrica das replicações;
- lembra qunado exclui o primeiro objeto e ele ficou como 'delete marked', essa opção permite que ele replique o arquivo nesse modo
- e o utlimo, replicar alterações de metadadados dos objetos...

---
### prints.
- após ele vai exibir configurações finais como:
![image](https://github.com/user-attachments/assets/cab6314c-40d1-4a59-8031-453d6f6acc4e)
- na primeira opção ele ja vai rodar o job de forma automática;
- na segunda opção, pode ser desabilitado a opção de criar reports de replicação;
![image](https://github.com/user-attachments/assets/aa633b52-a7b2-469b-b143-31efa0636b00)
- é exibido as policies configuradas para o s3...

![image](https://github.com/user-attachments/assets/9c44bf77-fbb0-4a6d-b554-bbc12bdaee76)
- o estado em vai preparar depois de algum tempo ele estará 'completed'
![image](https://github.com/user-attachments/assets/048fe960-d092-465d-8600-a14c71e1812d)

só salvar...
- por fim, o que for colocado no bucket principal, será replicado automaticamente para o bucket de Ohio.

stay focused.





#### Lifecycle do S3 é um conjunto de regras que você pode definir para automatizar a transição de objetos entre diferentes classes de armazenamento do S3 e, eventualmente, a exclusão de objetos.

#Movendo....
## Passo 1 - localizando a opção
![image](https://github.com/user-attachments/assets/278a3e05-7bcc-4a7e-b5b0-e7e6351fe68f)
- Acessar bucket > Gerenciamento > Regras de ciclo de vida > Criar regra de ciclo de vida.

---
## Passo 2 - "destrinchando" as opções....
![image](https://github.com/user-attachments/assets/e16b1869-17a2-417d-afe0-a433d978b766)
- nome da regra....

- "Limitar o escopo desta regra usando um ou mais filtros":
-   Permite que você defina condições específicas para quais objetos a regra se aplica, ou seja, você pode aplicar a regra apenas a um subconjunto de objetos dentro do bucket.
-   Se você quiser que uma regra de ciclo de vida seja aplicada apenas aos arquivos que estão na pasta imagens/ do seu bucket, você usaria um filtro que aplica essa regra apenas a esses arquivos.

- "Aplicar a todos os objetos no bucket"
-  Essa opção significa que a regra de ciclo de vida será aplicada a todos os objetos dentro do bucket, sem qualquer filtragem.

---
![image](https://github.com/user-attachments/assets/40a5800f-06b7-4b41-8738-e7863d4c241a)
- O prefixo é basicamente um "caminho" ou "pasta" dentro do seu bucket. O S3 organiza os arquivos de maneira hierárquica usando esse prefixo. Por exemplo:
-   Se você tem um bucket chamado meu-bucket, e dentro dele você tem uma pasta chamada imagens/, o prefixo seria imagens/.
-   Se você tem arquivos organizados assim:
-     imagens/foto1.jpg
-     imagens/foto2.jpg
-     documentos/texto.txt
- Quando você aplica um filtro de prefixo com o valor imagens/, a regra de ciclo de vida afetará somente os arquivos que começam com esse prefixo. Ou seja, apenas foto1.jpg e foto2.jpg seriam afetados pela regra de ciclo de vida, e documentos/texto.txt ficaria de fora.

---
- Tamanho do objeto
![image](https://github.com/user-attachments/assets/2d96ffd5-1526-43aa-bacb-bee80cfb0684)
- Você pode configurar a regra de ciclo de vida para ser aplicada somente aos objetos que têm um tamanho maior do que um valor especificado.

---
![image](https://github.com/user-attachments/assets/85e31c39-bf0f-44dd-bac4-2a71957af3d2)
-Ações de regras de ciclo de vida:  você pode definir ações específicas que determinam o que deve ser feito com os objetos dentro do bucket, dependendo de seu tempo de vida e seu status.
- transição de versões vai moder entre as diferentes classes, nela você vai definir para qual classe e a partir de quantos dias (os dias mínimos vão depender da classe escolhida)
![image](https://github.com/user-attachments/assets/9477b48c-44ba-4600-ba68-1fc5af96e4a8)

![image](https://github.com/user-attachments/assets/d4e51e5d-ac8b-4911-a205-f3a73ffb5b4a)
- no final é exibido uma prévia do ciclo de vida...

-----
# Excluindo....
![image](https://github.com/user-attachments/assets/787002d3-1218-443d-8550-f0faa3867ce4)
![image](https://github.com/user-attachments/assets/13c628a9-3d5c-4dd5-a919-ee3550c01cdd)
- depois de 15 dias os arquivos serão expirados e depois de 30, excluídos!

- depois é só clicar em criar regra!!



stay focused!









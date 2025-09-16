# 📖 Quiz Bíblico

Projeto desenvolvido no **Santander Code Girls 2025**, em parceria com a **DIO**. 
Este é um aplicativo de **quiz sobre a Bíblia**, feito para estudo e diversão.  
O objetivo é oferecer perguntas e respostas interativas sobre histórias, personagens e ensinamentos bíblicos.



## 🚀 Tecnologias Utilizadas
- **Frontend:** HTML, CSS e JavaScript (pode ser adaptado para mobile/web)
- **Backend:** API hospedada em instância **Amazon EC2**
- **Banco de Dados:** Amazon RDS (para guardar perguntas, respostas e pontuação dos jogadores)
- **Armazenamento de mídias:** Amazon S3 (para imagens/áudios do quiz)
- **Armazenamento de dados da instância:** Amazon EBS
- **DNS:** Amazon Route 53
- **Distribuição de conteúdo:** Amazon CloudFront



## 🏗️ Arquitetura (desenho feito no draw.io)

A arquitetura do app foi desenhada no **draw.io** usando os ícones da AWS.  
Ela mostra como os serviços da AWS se conectariam entre si para rodar o Quiz Bíblico:

1. **SHE.USER** acessa o app/web pelo navegador ou celular.  
2. A requisição vai para o **Route 53**, que resolve o nome do domínio.  
3. O tráfego passa pelo **CloudFront** (CDN), que acelera o acesso.  
4. O **EC2** recebe as requisições da API e roda a aplicação.  
   - Cada instância EC2 tem um volume **EBS** conectado para armazenar dados do servidor.  
5. O **EC2** conversa com:  
   - **RDS** para perguntas, respostas e ranking.  
   - **S3** para arquivos de mídia (imagens/áudios).  
6. Se uma instância cair, o balanceamento e o autoscaling garantem alta disponibilidade.



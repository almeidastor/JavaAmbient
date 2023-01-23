# Instalação e configuração para Desenvolvimento Java Netbeans/Xampp/Tomcat

<p align="justify"> Tutorial adaptado do Video <a href="https://www.youtube.com/watch?v=1zaKXUH1XXU">"Configuração da IDE Netbeans Apache para desenvolvimento Java / PHP com MySQL"</a> de Anderson Pazin.
Agradeço profundamente pelo material postado.


### Sumário
🔹 [Arquivos de Instalação](#arquivos-de-instalação)

🔹 [Instalação](#instalação)

🔹 [Configuração TOMCAT](#configuração-TOMCAT)

🔹 [Rodando a aplicação](#rodando-a-aplicação)

🔹 [Telas](#telas)


## Arquivos de Instalação 
<p align="justify">
<a href="https://www.oracle.com/br/java/technologies/downloads/#java11">JDK11</a>
</p>
<p align="justify">
<a href="https://netbeans.apache.org/download/">NETBEANS</a>
</p>
<p align="justify">
<a href="https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/7.3.0/xampp-win32-7.3.0-0-VC15-installer.exe/download">XAMPP 7.3</a>
</p>
<p align="justify">
<a href="https://tomcat.apache.org/download-10.cgi">TOMCAT10</a>
</p>


## Instalação
<p align="justify">
Instale os arquivos apenas avançando os passos
</p>

 <p align="center"> Configurações para instalação do TOMCAT </p>
<p align="center"> User Name: admin</p>
 <p align="center"> Password: admin</p>
 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/configtomcat.png"></p>



## Configuração TOMCAT
No Menu Iniciar, procure na lista por uma pasta chamada "Apache Tomcat 10.0 Tomcat10" e execute "Monitor Tomcat" (pode deixar esse atalho no desktop porque através dele que vamos iniciar o servidor sempre que precisarmos). Então na tela do aplicativo você pode escolher a opção de iniciar manualmente pela opção "MANUAL" ou "Automatic" para iniciar o servidor sempre automaticamente. Então aperte o botão "Start"

 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/apacheconf2.png"></p>

 Você pode testar se o servidor conectou através do endereço <a href="http://localhost:8089/">localhost:8089</a>


 Abra o NetBeans e procure a aba "Services" a opção de "Server" e em cima da opção, clique com botão direito do mouse em "Add Server"
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/confnettom.png"></p>


  Então escolha a opção "Apache Tomcat ou TomEE" e avance as opções
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/apaEEopt.png"></p>

A proxima opção a exibir seria para instanciar o Servidor

- Na opção de "Server Location" localize o caminho C:\Program Files\Apache Software Foundation\Tomcat 10.0
- Para a opção das credenciais, pare a execução do servidor (opção "Stop" em "Monitor Tomcat") e entre no diretório C:\Program Files\Apache Software Foundation\Tomcat 10.0\conf\
- Localize o arquivo "tomcat-users" e abra no bloco de notas
- Antes de "</tomcat-users>" cole o bloco
  <role rolename="manager-script"/>
  <user username="netbeans" password="netbeans" roles="manager-script"/>
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/rolebloque.png"></p>









## Rodando a aplicação

  

## Telas


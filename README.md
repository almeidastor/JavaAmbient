# Instalação e configuração para Desenvolvimento Java Netbeans/Xampp/Tomcat

<p align="justify"> Tutorial adaptado do Video <a href="https://www.youtube.com/watch?v=1zaKXUH1XXU">"Configuração da IDE Netbeans Apache para desenvolvimento Java / PHP com MySQL"</a> de Anderson Pazin.
Agradeço profundamente pelo material postado.


### Sumário
🔹 [Arquivos de Instalação](#arquivos-de-instalação)

🔹 [Instalação](#instalação)

🔹 [Configuração TOMCAT](#configuração-TOMCAT)

🔹 [Configurando TOMCAT E NETBEANS](#configurando-TOMCAT-E-NETBEANS)

🔹 [Testes](#testes)





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

<H3>TomCat</H3>

 <p align="center"> Configurações para instalação do TOMCAT </p>
<p align="center"> User Name: admin</p>
 <p align="center"> Password: admin</p>
 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/configtomcat.png"></p>


 <h3>Xampp</H3>
 Deixar apenas as opções de "MySQL" "Perl" e "phpMyAdmin" e avance as etapas
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/xampconfig.png"></p>

No painel principal, inicie as opções de Apache e MySQL e permita o acessos se necessário
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/xampconfig2.png"></p>

 Você pode testar se o servidor conectou através do endereço <a href="http://localhost/">localhost</a>
 O banco de dados pode ser usado em  <a href="https://localhost/phpmyadmin/">phpmyadmin</a>


## Configuração TOMCAT
No Menu Iniciar, procure na lista por uma pasta chamada "Apache Tomcat 10.0 Tomcat10" e execute "Monitor Tomcat" (pode deixar esse atalho no desktop porque através dele que vamos iniciar o servidor sempre que precisarmos). Então na tela do aplicativo você pode escolher a opção de iniciar manualmente pela opção "MANUAL" ou "Automatic" para iniciar o servidor sempre automaticamente. Então aperte o botão "Start"

 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/apacheconf2.png"></p>

 Você pode testar se o servidor conectou através do endereço <a href="http://localhost:8089/">localhost:8089</a>


## Configurando TOMCAT E NETBEANS

 Abra o NetBeans e procure a aba "Services" a opção de "Server" e em cima da opção, clique com botão direito do mouse em "Add Server"
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/confnettom.png"></p>


  Então escolha a opção "Apache Tomcat ou TomEE" e avance as opções
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/apaEEopt.png"></p>

A proxima opção a exibir seria para instanciar o Servidor

- Na opção de "Server Location" localize o caminho C:\Program Files\Apache Software Foundation\Tomcat 10.0
- Para a opção das credenciais, pare a execução do servidor (opção "Stop" em "Monitor Tomcat") e entre no diretório C:\Program Files\Apache Software Foundation\Tomcat 10.0\conf\
- Localize o arquivo "tomcat-users" e abra no bloco de notas
- Antes de "< /tomcat-users>" cole o bloco abaixo e salve (tire o espaço)
  <p>< role rolename="manager-script"/></p>
  <p>< user username="netbeans" password="netbeans" roles="manager-script"/>"</p>
<p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/rolebloque.png"></p></code>

- Atualize as credenciais
<p align="center"> Server Location: C:\Program Files\Apache Software Foundation\Tomcat 10.0</p>
<p align="center"> User Name: netbeans</p>
 <p align="center"> Password: netbeans</p>

 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/instancenet.png"></p>

E Vá na opção "Finish"

Então na opção de "Server" clique com o botão direito em "Start" e permita alguns acessos se necessário
 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/netbenasaccss.png"></p>

 <p>Caso novamente peça senha, utilize as credenciais </p>
 <p>User Name: netbeans</p>
 <p>Password: netbeans</p>

 <p>Esse mecanismo dá o poder ao Netbeans de iniciar o Servidor (Cuidado ao iniciar pelo Netbeans e pelo Monitor porque podem dar conflito)


  ## Testes

  <h3>TomCat</h3>

  Em NetBeans:
  File > New Project > Java With Maven > Web Application

 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/webtest.png"></p>

 Espere o carregamento do servidor e escolha a opção Index.html que está na pasta Web Pages do projeto

  <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/webtest2.png"></p>

  Então execute o Código no Netbeans

    <h3>Xampp</h3>
- Acesse  <a href="https://localhost/phpmyadmin/">phpmyadmin</a>
- Então crie um banco de dados de nome "bd_cafe_fatec" em "utf8_general_ci" 
- Cole o seguinte bloco de código na opção de SQL:

USE bd_cafe_fatec;
CREATE USER 'fatec'@'localhost' Identified by 'aulafatec';
GRANT ALL PRIVILEGES ON bd_cafe_fatec.* TO 'fatec'@'localhost';
FLUSH PRIVILEGES;

CREATE TABLE `bebidas` (
  `idBebida` int(5) NOT NULL,
  `nome` varchar(50) NOT NULL,
  `tipo` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

--
ALTER TABLE `bebidas`
  ADD PRIMARY KEY (`idBebida`);

INSERT INTO `bebidas` (`idBebida`, `nome`, `tipo`) VALUES
(1, 'Café Espresso', 'Cafés'),
(2, 'Mocca Latte', 'Cafés'),
(3, 'Capuccino', 'Cafés'),
(5, 'Coca-cola', 'Refrigerantes'),
(7, 'Suco de Laranja', 'Sucos Naturais'),
(8, 'Suco de Uva', 'Sucos Naturais'),
(9, 'Chocolate Quente', 'Cafés'),
(10, 'Guaraná', 'Refrigerantes');

 Em NetBeans (PHP):

File > New Project > PHP > PHP Application > Next > Next > Finish

 <p align="center"> <img src="https://github.com/almeidastor/JavaAmbient/blob/main/imagens/webtest3.png"></p>

 após selecionar a página index.php, localize o começo de bloco do código de php, coloque:
        <?php
        $host = "localhost";
        $user = "fatec";
        $pass = "aulafatec";
        $banco = "bd_cafe_fatec";
        
        $conexao = mysqli_connect($host, $user, $pass) or die ("Erro ao conectar");
        $bd = mysqli_select_db($conexao, $banco) or die ("Erro ao escolher bd");
        
        $qry = "SELECT * FROM bebidas ORDER BY tipo, nome";
        
        $sqlExec = mysqli_query($conexao, $qry) or die (mysqli_error($conexao));
        
        while ($linha = mysqli_fetch_assoc($sqlExec)){
            echo $linha['idBebida']." - ". utf8_encode($linha['nome'])
                    ."(". utf8_encode($linha['tipo']).")<br/>";
        }
        ?>
    
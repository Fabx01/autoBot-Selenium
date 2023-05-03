# autoBot-Selenium
códigos de automação utilizando a linguagem Java ,Selenium e WebDrive


# Tutorial de Automação Web com Eclipse, Java e Selenium WebDriver

Neste tutorial, vamos ensinar como criar um projeto de automação de testes para web usando a IDE Eclipse com a linguagem Java e a biblioteca Selenium WebDriver.

## Pré-requisitos

Para seguir este tutorial, você precisa ter os seguintes pré-requisitos instalados no seu computador:

- [Java SE Development Kit (JDK)](https://www.oracle.com/java/technologies/javase-downloads.html)
- [Eclipse IDE](https://www.eclipse.org/downloads/)
- [Selenium WebDriver](https://www.selenium.dev/downloads/)
- [ChromeDriver](https://chromedriver.chromium.org/downloads) (ou outro driver de navegador de sua escolha)

## Etapa 1: Configuração do ambiente

### 1.1 Instalando o Java SE Development Kit (JDK)

Baixe e instale a versão mais recente do JDK do site da Oracle. Após a instalação, você pode verificar se a instalação foi bem-sucedida abrindo o terminal e digitando o seguinte comando:

```
java -version
```

Se a instalação estiver correta, você verá a versão do JDK instalada no seu computador.

### 1.2 Instalando o Eclipse IDE

Baixe e instale o Eclipse IDE do site oficial. Você pode escolher qualquer versão que desejar.

### 1.3 Configurando o projeto no Eclipse

1. Abra o Eclipse IDE
2. Crie um novo projeto Java clicando em "File" > "New" > "Java Project"
3. Dê um nome para o seu projeto e clique em "Finish"
4. Clique com o botão direito do mouse na pasta do seu projeto e selecione "New" > "Package"
5. Dê um nome para o seu pacote e clique em "Finish"

### 1.4 Baixando o Selenium WebDriver

Baixe o Selenium WebDriver do site oficial e extraia o arquivo zip em um diretório da sua escolha.

### 1.5 Baixando o ChromeDriver

Baixe o ChromeDriver do site oficial e extraia o arquivo zip em um diretório da sua escolha.

## Etapa 2: Criando o primeiro teste

### 2.1 Adicionando as dependências do Selenium WebDriver

1. Clique com o botão direito do mouse na pasta do seu projeto e selecione "Properties"
2. Clique em "Java Build Path" > "Libraries" > "Add External JARs"
3. Navegue até o diretório onde você extraiu o arquivo do Selenium WebDriver e selecione o arquivo "selenium-java-X.XX.jar"
4. Clique em "OK" para confirmar

Claro, vamos continuar o tutorial.

### 2.2 Escrevendo o primeiro teste

Agora que já temos o projeto criado e as bibliotecas do Selenium adicionadas, podemos começar a escrever o nosso primeiro teste.

Crie uma nova classe chamada `GoogleSearchTest` dentro do pacote `tests`. Essa classe será responsável por testar a funcionalidade de busca do Google.

```java
package tests;

import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class GoogleSearchTest {
    
    @Test
    public void testGoogleSearch() {
        // Configura o driver do Chrome
        System.setProperty("webdriver.chrome.driver", "caminho/para/chromedriver");
        WebDriver driver = new ChromeDriver();
        
        // Navega até a página do Google
        driver.get("https://www.google.com.br/");
        
        // Encontra o campo de busca e digita o termo de pesquisa
        WebElement searchBox = driver.findElement(By.name("q"));
        searchBox.sendKeys("Selenium WebDriver");
        
        // Encontra o botão de busca e clica nele
        WebElement searchButton = driver.findElement(By.name("btnK"));
        searchButton.click();
        
        // Fecha o navegador
        driver.quit();
    }
}
```

Neste teste, estamos configurando o driver do Chrome, navegando até a página do Google, pesquisando por "Selenium WebDriver" e clicando no botão de busca. Finalmente, fechamos o navegador.

### 2.3 Executando o teste

Agora que o teste está escrito, podemos executá-lo e ver se tudo está funcionando corretamente.

Clique com o botão direito na classe `GoogleSearchTest` e selecione `Run As > JUnit Test`. Isso iniciará o driver do Chrome e executará o teste. 

Se tudo der certo, o navegador deve abrir e realizar a pesquisa no Google automaticamente. Depois que o teste for concluído, o navegador será fechado.

Parabéns! Você acabou de escrever e executar o seu primeiro teste de automação com o Selenium.

## 3. Conclusão

O Selenium é uma ferramenta poderosa para a automação de testes de software. Com ele, podemos escrever scripts de teste automatizados que simulam a interação do usuário com o navegador. Isso nos permite testar nossos aplicativos web de forma mais eficiente e eficaz.

Neste tutorial, você aprendeu como configurar um ambiente de desenvolvimento para o Selenium usando o Eclipse e o Maven, como escrever e executar um teste básico de automação usando o Selenium WebDriver e como localizar elementos na página usando o WebDriver.

Lembre-se de que esta é apenas uma introdução ao Selenium e que há muito mais recursos e recursos disponíveis para explorar. Portanto, continue praticando e aprendendo!

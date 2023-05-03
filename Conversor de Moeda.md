
### conversor de moeda usando os dados da pagina do google


Para reescrever o código em uma versão usando linguagem Java e Selenium, será necessário instalar o WebDriver do Selenium para a utilização do navegador. 
Segue abaixo uma possível implementação:

```java
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.net.URLEncoder;
import java.util.Scanner;

public class ConversorMoeda {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String googleUrl = "https://www.google.com/search?q=";
        System.out.print("Informe uma moeda base: ");
        String baseCurrency = scanner.nextLine().isEmpty() ? "dolar" : scanner.nextLine();
        System.out.print("Informe uma moeda desejada: ");
        String targetCurrency = scanner.nextLine().isEmpty() ? "real" : scanner.nextLine();
        String searchUrl = googleUrl + URLEncoder.encode(baseCurrency + " para " + targetCurrency);

        System.setProperty("webdriver.chrome.driver", "caminho/para/chromedriver");
        WebDriver driver = new ChromeDriver();
        try {
            System.out.println("Iniciando conversão...");
            driver.get(searchUrl);

            WebElement resultElement = driver.findElement(By.cssSelector(".lWzCpb.a61j6"));
            String result = resultElement.getAttribute("value").trim();

            System.out.println("O valor de 1 " + baseCurrency + " em " + targetCurrency + " é " + result);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        } finally {
            driver.quit();
        }
    }
}
```

No código acima, utilizamos a classe `ChromeDriver` para instanciar um driver do Chrome. 
É necessário informar o caminho para o arquivo executável do driver na linha 
`System.setProperty("webdriver.chrome.driver", "caminho/para/chromedriver");`. 
Além disso, utilizamos os métodos `findElement(By.cssSelector(...))` e `getAttribute("value")` 
para obter o valor da conversão a partir do elemento HTML selecionado pelo seletor CSS `.lWzCpb.a61j6`.


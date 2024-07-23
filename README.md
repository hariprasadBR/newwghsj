package praticw;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.List;

public class selniumpract1 {

    public static void main(String[] args) throws InterruptedException {


        WebDriver driver = new ChromeDriver();

        driver.get("https://www.iplt20.com/stats/2024");

       List<WebElement> columns= driver.findElements(By.xpath("(//tr[@class='st-table__head'])[1]//child::th"));

        List<WebElement> rows= driver.findElements(By.xpath("//tr"));

        System.out.println(rows.size());
 int count=0;

        for(WebElement a1:rows){
//           System.out.println(a1.getAttribute("class"));

            String  className = a1.getAttribute("class");
//            System.out.println(className);

           if (className.contains("RCB")){

               System.out.println(count);
               System.out.println(a1.getAttribute("class"));
               WebElement names=driver.findElement(By.xpath("(//tr//child::a//child::div[@class='st-ply-name ng-binding'])["+count+"]"));

               System.out.println( names.getText());
            count++;

           }
        count++;
       }

        Thread.sleep(9000);
        driver.quit();

    }
}

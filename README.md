package Workout_Program;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class FrameHandling {

	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver","F:\\Chromedriver.exe");		WebDriver driver=new ChromeDriver();

		driver.manage().window().maximize();

		driver.manage().timeouts().implicitlyWait(2000,TimeUnit.SECONDS);

		driver.get("https://www.rediff.com");
		
		// Switch to frame using index
		driver.switchTo().frame(0);
		WebElement value=driver.findElement(By.id("bseindex"));
		System.out.println(value.getText());
		driver.switchTo().defaultContent();
		//Switch to frame using ID or Name
		driver.switchTo().frame("moneyiframe");
		WebElement value1=driver.findElement(By.id("bseindex"));

		System.out.println(value1.getText());
//
//		driver.switchTo().defaultContent();
//
//		driver.findElement(By.linkText("Sign in")).click();
//		driver.switchTo().frame("moneyiframe");
//		WebElement value=driver.findElement(By.id("bseindex"));
//
//		System.out.println(value.getText());


	}

}


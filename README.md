# Automation_Task
Web Script



package testing;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

import io.github.bonigarcia.wdm.WebDriverManager;

public class claass 
{
	public static String browser = "chrome";
	public static WebDriver driver;
	public static void main(String[] args) throws InterruptedException 
	{
		if (browser.equals("chrome")) 
		{
			WebDriverManager.chromedriver().setup();
			driver = new ChromeDriver();
		}
		else if (browser.equals("Firefox"))
		{
			WebDriverManager.firefoxdriver().setup();
			driver = new FirefoxDriver();
		}
		driver.get("https://unicreds.com/contact-us");
		driver.findElement(By.id("fullname")).sendKeys("random name");
		driver.findElement(By.xpath("//*[@id=\"__next\"]/div[2]/section/div/div[2]/div[2]/div[2]/div/form/input[2]")).sendKeys("random@gmail.com");
		driver.findElement(By.xpath("//*[@id=\"__next\"]/div[2]/section/div/div[2]/div[2]/div[2]/div/form/select")).findElements(By.xpath("//*[@id=\"__next\"]/div[2]/section/div/div[2]/div[2]/div[2]/div/form/select/option[1]"));
		driver.findElement(By.id("phone")).sendKeys("9456777778");
		driver.findElement(By.id("message")).sendKeys("writing this to test the page");
		Thread.sleep(5000);
		//driver.findElement(By.id("contactButton")).click();
		driver.findElement(By.id("__next")).click();
		Thread.sleep(5000);
		driver.findElement(By.name("email")).sendKeys("verify@gmail.com");
	}
}

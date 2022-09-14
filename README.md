# testing-frugal
package software;
 import java.time.Duration;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.By;
public class TC001 {

	WebDriver driver;
	             public void launchrowser() throws InterruptedException {
	                 	System.setProperty("webdriver.chrome.driver", "E:\\driver\\chromedriver_win32\\chromedriver.exe\\");
		             driver = new ChromeDriver();
	                   	driver.get("https://www.makemytrip.com/railways/");
		
	                           	String title = driver.getTitle();
	                    	System.out.println("Title of the page is: " + title);
	                      	String url = driver.getCurrentUrl();
	                  	System.out.println("URL of the page is: " + url);

		
		driver.findElement(By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[1]/label/span")).click();
		

		Thread.sleep(1000);
		driver.findElement(
				By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[1]/div[1]/div/div/div/input"))
				.sendKeys("Delhi");
		
		Thread.sleep(2000);

		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

		
		int length = driver.findElements(By.cssSelector("ul.react-autosuggest__suggestions-list > li")).size();
		System.out.println("Length of the list is: " + length);

	
		for (int i = 0; i < length; i++) {
			
			String element = driver.findElements(By.cssSelector(
					"ul.react-autosuggest__suggestions-list > li > div > div > p.searchedResult.font14.darkText > span"))
					.get(i)
					.getText();
			System.out.println("Element is: " + element);
		
			if (element.equals("Delhi")) {
				
				driver.findElements(By.cssSelector(
						"ul.react-autosuggest__suggestions-list > li > div > div > p.searchedResult.font14.darkText > span"))
						.get(i).click();
				break;
			}
		}

		
		driver.findElement(By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[2]/label/span")).click();
		

		Thread.sleep(1000);
		driver.findElement(
				By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[2]/div[1]/div/div/div/input"))
				.sendKeys("Lucknow");
		
		Thread.sleep(2000);

		
		length = driver.findElements(By.cssSelector("ul.react-autosuggest__suggestions-list > li")).size();
		System.out.println("Length of the list is: " + length);

		
		for (int i = 0; i < length; i++) {
		
			String element = driver.findElements(By.cssSelector(
					"ul.react-autosuggest__suggestions-list > li > div > div > p.searchedResult.font14.darkText > span"))
					.get(i)
					.getText();
			System.out.println("Element is: " + element);
			
			if (element.equals("Lucknow")) {
				// click on the element
				driver.findElements(By.cssSelector(
						"ul.react-autosuggest__suggestions-list > li > div > div > p.searchedResult.font14.darkText > span"))
						.get(i).click();
				break;
			}
		}

		
		Thread.sleep(2000);
		driver.findElement(By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[3]")).click();
		Thread.sleep(1000);
		driver.findElement(By.xpath(
				"//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[3]/div[1]/div/div/div/div[2]/div/div[2]/div[1]/div[3]/div[3]/div[6]"))
				.click();

		
		Thread.sleep(2000);
		driver.findElement(By.xpath("//*[@id='root']/div/div[2]/div/div/div/div[2]/div/div[4]")).click();
		length = driver.findElements(By.cssSelector("ul.travelForPopup > li")).size();
		System.out.println("Length of the list is: " + length);
		for (int i = 0; i < length; i++) {
			String element = driver.findElements(By.cssSelector("ul.travelForPopup > li")).get(i).getText();
			System.out.println("Element is: " + element);
			if (element.equals("Third AC")) {
				driver.findElements(By.cssSelector("ul.travelForPopup > li")).get(i).click();
				break;
			}
		}

		
		Thread.sleep(2000);
		driver.findElement(By.xpath("// *[@id='root']/div/div[2]/div/div/div/div[2]/p/a")).click();
		driver.close();

	}

	public static void main(String[] args) throws InterruptedException {
	TC001 obj = new TC001();
obj.launchrowser();
		
	}

	
		
	}
	


 Context:
    You are an AI assistant to convert DOM to selenium java code for leaftaps.
   
    Given the following DOM structure:
  
    Write complete test to run in VS code

Instructions:

     - Implementation guidelines:
       - Java 8+ features if appropriate
       - Use Selenium 2.30 or above version
       - Import required classes
       - Add JavaDoc for methods & class
       - [MANDATORY] Every method should have proper comments above method signature
       - Do not send any explanation or additional text
       - Use selectByVisibleText for dropdowns
       - [CRITICAL] use right locators starting id, name, class, link text and finally xpath

Examples:

     - Example 1:
      
      Input DOM:
      <form id="login" method="post" action="/opentaps/control/login">
        <p class="top">
          <label for="username">Username</label>
          <input class="inputLogin" type="text" id="username" name="USERNAME" size="50">
        </p>
        <p>
          <label for="password">Password</label>
          <input class="inputLogin" type="password" id="password" name="PASSWORD" size="50">
        </p>

        <p>
          <input class="decorativeSubmit" type="submit" value="Login">
        </p>
      </form>

      Selenium Java Page Object Class:
      \`\`\`java
        package com.leaftaps.ui.pages;


        import java.time.Duration;

        import org.openqa.selenium.By;
        import org.openqa.selenium.chrome.ChromeDriver;

        import io.github.bonigarcia.wdm.WebDriverManager;

        public class Login {
          
          public static void main(String[] args) {
            /*
            * Class Name: Login
            */
            
            // Step 1) Launch the chrome browser (Class Name -> ChromeDriver)
            ChromeDriver driver = new ChromeDriver();
            
            // Step 2) Load the URL (http://leaftaps.com/opentaps/control/main) -> get
            driver.get("http://leaftaps.com/opentaps");
            
            // Step 2b) Add common time to wait for all/any elements to load (Write once)
            driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(15));
            
            // Step 3) Maximize the chrome browser
            driver.manage().window().maximize();
            
            // Step 4) Find the username and type the value (DemoSalesManager)
            driver.findElement(By.id("username1")).sendKeys("DemoSalesManager");
            
            // Step 5) Find the password and type the value (crmsfa)
            driver.findElement(By.id("password")).sendKeys("crmsfa");	
            
            // Step 6) Find the login button and click
            driver.findElement(By.className("decorativeSubmit")).click();
            
            // Step 7) Verify the title 
            String title = driver.getTitle();
            System.out.println(title);

          }

        }
        ```          
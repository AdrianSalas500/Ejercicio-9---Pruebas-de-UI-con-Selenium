# Ejercicio-9---Pruebas-de-UI-con-Selenium


# Parte B - Implemente los casos de prueba WebDriver. Describa brevemente los cambios principales que ha tenido que hacer al código exportado por Selemium IDE/Kantalon (si es que ha habido alguno). Si no quieren repetir código, pueden crear helper methods.


## 1. He tenido que añadir estas dependencias al pom.xml:

```xml
 <dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>4.0.0</version>
 </dependency>

<dependency>
  <groupId>io.github.bonigarcia</groupId>
  <artifactId>webdrivermanager</artifactId>
  <version>5.0.3</version>
  <scope>test</scope>
</dependency>
```
## 2. Añadí un import al código exportado

```java
import io.github.bonigarcia.wdm.WebDriverManager;
```
## 3. Añadí en la función setUp() varías líneas (están comentadas):

```java
 @Before
 public void setUp() {
  System.setProperty("webdriver.chrome.driver","ide\\chromedriver.exe"); // Linea añadida 1: Indicating where the Chrome driver executable is stored.
  WebDriverManager.chromedriver().setup(); // Linea añadida 2: Calling setup() automatically puts the correct browser driver where the code will see it
  driver = new ChromeDriver();
  js = (JavascriptExecutor) driver;
  vars = new HashMap<String, Object>();
 }
 ```

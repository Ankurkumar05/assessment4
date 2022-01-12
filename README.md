# assessment4
WebDriver d;
	@Before
	public void setUp() throws Exception {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\ankur.kumar05\\Documents\\chromedriver_win32\\chromedriver.exe");
        d = new ChromeDriver();
        d.get("http://automationpractice.com/index.php");
        d.manage().window().maximize();
        d.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
	}
	@After
	public void tearDown() throws Exception {
		d.quit();
	}
	@Test
	public void test() throws Exception {
		d.findElement(By.xpath("//*[@id=\"header\"]/div[2]/div/div/nav/div[1]/a")).click();
		d.findElement(By.id("email_create")).sendKeys("xyz@gmail.com");
		d.findElement(By.xpath("//*[@id=\"SubmitCreate\"]/span")).click();	
		d.findElement(By.xpath("//*[@id=\"account-creation_form\"]/div[1]/div[1]/div[1]/label")).click();	
		d.findElement(By.xpath("//*[@id=\"customer_firstname\"]")).sendKeys("Ankur");	
		d.findElement(By.xpath("//*[@id=\"customer_lastname\"]")).sendKeys("kumar");
		d.findElement(By.id("passwd")).sendKeys("KumaRa");		
		d.findElement(By.id("address1")).sendKeys("chandigarh");	
		d.findElement(By.id("city")).sendKeys("chandigarh");
		WebElement dd=d.findElement(By.id("id_state"));
		Select sel=new Select(dd);               
		sel.selectByIndex(2);  
		d.findElement(By.id("postcode")).sendKeys("140603");	
		d.findElement(By.id("phone_mobile")).sendKeys("8572881907");
		WebElement text1=d.findElement(By.xpath("//*[@id=\"center_column\"]/div/ol/li"));
		String ExpectedText="The Zip/Postal code you've entered is invalid. It must follow this format: 00000";
		Assert.assertTrue(ExpectedText.equals(text1));
		d.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
		}	
	@Test
	public void test1() throws Exception {
		d.findElement(By.xpath("//*[@id=\"header\"]/div[2]/div/div/nav/div[1]/a")).click();
		d.findElement(By.id("email")).sendKeys("ankurkumar097@gmail.com");
		d.findElement(By.id("passwd")).sendKeys("KumaRa");
		d.findElement(By.xpath("//*[@id=\"SubmitLogin\"]/span")).click();		
		d.findElement(By.xpath("//*[@id=\"block_top_menu\"]/ul/li[3]/a")).click();		
		d.findElement(By.xpath("//*[@id=\"center_column\"]/ul/li/div/div[2]/h5/a")).click();
		d.findElement(By.xpath("//*[@id=\"add_to_cart\"]/button/span")).click();	
		d.findElement(By.xpath("//*[@id=\"layer_cart\"]/div[1]/div[2]/div[4]/a/span")).click();	
		d.findElement(By.xpath("//*[@id=\"center_column\"]/p[2]/a[1]/span")).click();
		d.findElement(By.xpath("//*[@id=\"center_column\"]/form/p/button/span")).click();	
		d.findElement(By.xpath("//*[@id=\"cgv\"]")).click();
		d.findElement(By.xpath("//*[@id=\"form\"]/p/button/span")).click();
		d.findElement(By.xpath("//*[@id=\"HOOK_PAYMENT\"]/div[1]/div/p/a")).click();
		d.findElement(By.xpath("//*[@id=\"cart_navigation\"]/button/span")).click();
		d.findElement(By.xpath("//*[@id=\"header\"]/div[2]/div/div/nav/div[1]/a/span")).click();	
		d.findElement(By.xpath("//*[@id=\"center_column\"]/div/div[1]/ul/li[1]/a/span")).click();	
		d.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
	}

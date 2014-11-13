using System;
using Microsoft.VisualStudio.TestTools.UnitTesting;
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using OpenQA.Selenium.Interactions;

namespace UnitTestProject6
{
    [TestClass]
    public class UnitTest1
    {
        IWebDriver driver;
        [TestMethod]
        public void O2Test()
        {

            driver = new ChromeDriver(@"C:\Selenium\");
            driver.Navigate().GoToUrl("https://www.o2.co.uk");
            driver.Manage().Window.Maximize();
            System.Threading.Thread.Sleep(10000);
           if (driver.FindElements(By.Id("no")).Count > 0)
                driver.FindElement(By.Id("no")).Click();

            Actions action = new Actions(driver);
            IWebElement we = driver.FindElement(By.XPath("//*[@id=\"pn5\"]/a/dl/dt"));
            action.MoveToElement(we).Build().Perform();
            if (driver.FindElements(By.Id("no")).Count > 0)
                driver.FindElement(By.Id("no")).Click();
            string browse = driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[1]/a")).Text;
            Assert.AreEqual(browse, "Browse Help");

            action.MoveToElement(we).Build().Perform();

            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[2]/a")).Text, "All Help topics");

            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[3]/a")).Text, "Contact us");

            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[4]/a")).Text, "O2 Gurus");

            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[5]/a")).Text, "O2 Community");
             driver.FindElement(By.XPath("//*[@id=\"pn5\"]/a/dl/dt"));
            action.MoveToElement(we).Build().Perform();
            driver.FindElement(By.XPath("//*[@id=\"pn5\"]/ul/li[3]/a")).Click();
            driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/h2/a")).Click();
           // selectElement(By.XPath("//*[@id=\"contacts-q26\"]/a"));
            IWebElement select = driver.FindElement(By.XPath("//*[@id=\"contacts-q26\"]/a"));
            driver.FindElement(By.XPath("//*[@id=\"contacts-q26\"]/a")).Click();
            //System.Threading.Thread.Sleep(20000);
            driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/h4/a")).Click();
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[1]/td[2]")).Text, "08:00 - 21:00");
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[1]/td[1]")).Text, "Monday - Friday");
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[2]/td[1]")).Text, "Saturday");
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[1]/td[1]")).Text, "08:00 - 20:00");
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[3]/td[1]")).Text, "Sunday");
            action.MoveToElement(we).Build().Perform();
            Assert.AreEqual(driver.FindElement(By.XPath("//*[@id=\"acc1\"]/div[2]/div/div/div[2]/div[3]/div[2]/div/div/div[2]/table/tbody/tr[3]/td[2]")).Text, "09:00 - 18:00");
            driver.Close();


        }

        private void selectElement(By by)
        {
            throw new NotImplementedException();
        }
    }
}

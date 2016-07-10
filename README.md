# keyword-driven-framework
package gmailpackage;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class Kdfm {
	WebDriver d;
public void openbrowser(String tdata){

	if(tdata.equalsIgnoreCase("FireFox")){
		d= new FirefoxDriver();
	}
	else if(tdata.equalsIgnoreCase("Crome")){
		d= new ChromeDriver();
	}
}
public void openurl(String tdata){
	d.get(tdata);
}
public void clickonlink(String ptype,String pvalue){
	By e;
	e=Weblocators(ptype,pvalue);
	d.findElement(e).click();
}
public void entertext(String ptype,String pvalue,String tdata){
	By e;
	e=Weblocators(ptype,pvalue);
	d.findElement(e).sendKeys(tdata);
}
public void clickonbutton(String ptype,String pvalue){
	By e;
	e=Weblocators(ptype,pvalue);
	d.findElement(e).click();	
}
public By Weblocators(String ptype, String pvalue){
	By b;
	switch(ptype){
	case "id":b=By.id(pvalue);
	break;
	case "name":b=By.name(pvalue);
	break;
	case "xpath":b=By.xpath(pvalue);
	break;
	default:
		b=null;
		break;
	}
	return b;
}
}

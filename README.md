# Web_Scraping_HTML_page
Scraping Data from simple HTML page
### **Web Scraping HTML Page:**
As there is a saying ‘Garbage in, Garbage Out’ in data science. That is good quality of data is necessary to get insights from it. Therefore, web scraping is essential part in getting good data.
### **What is Web Scraping:**
It is automation of retrieving unstructured data from websites then structure it and save it for later use. For example, you want to know locations of digital mailboxes available on ‘anytimemailbox’ then you might want to Scrape locations data from website.
### **Which websites you can scrape:**
Not all websites allow scraping as scraping increases the website traffic and may cause the website server to breakdown. To know websites scraping policy simply put ‘robots.txt’ after the website to know which sub sites or site are not allowed to scrape. Here is  ‘anytimemailbox.com’ website policy regarding scraping.
 
 ![image](https://user-images.githubusercontent.com/40564900/176701254-bf4bd338-018d-4488-8d73-f5e8b504fd30.png)
 
Here user-agent is for general users. Disallow is prohibited (legally) sub/sites for scraping. 
## **Scraping Working:**
Website scraping is simple, you send a request to server and get a response, in which data is present and is unstructured, then you manipulate the response data and get the required data and structure it.
### **How to scrape a website:**
1.	First inspect the website html that you want to scape. 
    a.	In browser right click in website and click inspect
    b.	Or you get site html using code and inspect it.
2.	Get html content of website by code using URL.
3.	Get data from html content by using tags, names, ids, or class.
4.	Organize the data in formats like excel, google sheets, word, pdf etc.
5.	Most of the time websites have data distributed in different pages then you have repeat from 2 to 4 for that but have to get the links for that pages from html     content got in step 2
### **Exception:**
it works for static website in which content does not changes and for dynamic websites in which content changes I-e gets data from certain server then the approach is different will be discussed later.
## **Libraries for Scraping:**
In python the most used libraries are requests and BeautifulSoup.
### **Requests:**
It is a python module in which you send http request to the website and get html content of website in response. You can use GET or POST requests. By sending GET request you get response object which contains html content.
### **BeautifulSoup:**
It is a library which helps you navigate html or XML content. It helps you search different elements and get their required data.
Web Scraping Example:
## **Problem Statement:**
I want to get all the available locations of digital mailboxes available on ‘anytimemailbox’.
## **Solution Approach:**
1.	Inspect website by right click in browser and select inspect.

     ![image](https://user-images.githubusercontent.com/40564900/176701330-15a5c5c1-41bd-46d7-832b-73277b740c65.png)
     ![image](https://user-images.githubusercontent.com/40564900/176701348-c2ed87f3-845d-4afb-bf1c-d1c6951b7d79.png)

      As I need the locations which are in other page by inspecting ‘Get Started’ I can see <a class=”btn theme-button” have ‘href=”/locations”’ which have link to         locations.
  
2.	Get HTML content using URL and from that content we will get link for locations.
      
      ![image](https://user-images.githubusercontent.com/40564900/176701468-40fba99d-fee1-4c1f-91ac-703c409f6f2b.png)

      Here is the html page content now we will search for link using tag ‘a’ and class name ‘btn theme-button. And there are multiple elements with this tag and           class so we will search for that which have ‘/locations’ as “href”.
  
      ![image](https://user-images.githubusercontent.com/40564900/176701686-ac4b6c95-3475-47d9-bf49-c250659b0e5a.png)
      ![image](https://user-images.githubusercontent.com/40564900/176701732-8f36007f-4520-4102-9d71-31131f9520e7.png)
      ![image](https://user-images.githubusercontent.com/40564900/176701763-2ee7371f-1be9-4b0f-a5fb-d7bdfc6dd0db.png)
 
      Now we can each country have cities and in them and in it the location details.
  
3.	Now we will get links for each country page.
       
       ![image](https://user-images.githubusercontent.com/40564900/176701845-a5c0983d-22d1-400e-ab5a-7c124484f104.png)
       
      By inspecting we can see the countries have tag ‘div’ and class ‘row theme-top-gap’ and in it tag ‘a’ have ‘href’ which have link.
  
4.	Now we will get links for each city present country.
       
      ![image](https://user-images.githubusercontent.com/40564900/176701909-b92b0075-5880-45aa-88f4-b7d053e6abd6.png)

      Each city link is in ‘href’ where it has tag ‘a’ and class ‘theme-subtle-link’.

5.	And each city has different location details which are present in tag ‘div’ and class ‘theme-location’-item’.
 
      ![image](https://user-images.githubusercontent.com/40564900/176701979-948bfd9f-cc5d-47c6-87f1-6687b7660d04.png)

6.	All this process is looped through to get data automatically.
7.	Required data is getting country name, city name, address title, full address, and price.
    
      ![image](https://user-images.githubusercontent.com/40564900/176702029-249d30d3-c388-4135-b2b4-713950a8f412.png)

8.	Then save the data in dictionary.
      
      ![image](https://user-images.githubusercontent.com/40564900/176702092-466a3b09-1936-4c9f-80ac-3cfaba052de0.png)

9.	And then change the data into excel.
 

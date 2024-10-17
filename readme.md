get_wiki_covid19_page <- function() {
    
  # Our target COVID-19 wiki page URL is: https://en.wikipedia.org/w/index.php?title=Template:COVID-19_testing_by_country  
  # Which has two parts: 
    # 1) base URL `https://en.wikipedia.org/w/index.php  
    # 2) URL parameter: `title=Template:COVID-19_testing_by_country`, seperated by question mark ?
    
  # Wiki page base
  wiki_base_url <-  "https://en.wikipedia.org/w/index.php"
  
  # You will need to create a List which has an element called `title` to specify which page you want to get from Wiki
   # in our case, it will be `Template:COVID-19_testing_by_country`
  wiki_params <- list(title = "Template:COVID-19_testing_by_country")
  
  
  # - Use the `GET` function in httr library with a `url` argument and a `query` arugment to get a HTTP response
   wiki_response <- GET(wiki_base_url, query = wiki_params) 
   
  # Use the `return` function to return the response
return(wiki_response)
}
Call the get_wiki_covid19_page function to get a http response with the target html page

# Call the get_wiki_covid19_page function and print the response
wiki_covid19_page_response <- get_wiki_covid19_page()

print(wiki_covid19_page_response)
## Response [https://en.wikipedia.org/w/index.php?title=Template%3ACOVID-19_testing_by_country]
##   Date: 2022-03-29 07:22
##   Status: 200
##   Content-Type: text/html; charset=UTF-8
##   Size: 413 kB
## <!DOCTYPE html>
## <html class="client-nojs" lang="en" dir="ltr">
## <head>
## <meta charset="UTF-8"/>
## <title>Template:COVID-19 testing by country - Wikipedia</title>
## <script>document.documentElement.className="client-js";RLCONF={"wgBreakFrames...
## "CS1 German-language sources (de)","CS1 Azerbaijani-language sources (az)","C...
## "CS1 uses Japanese-language script (ja)","CS1 Japanese-language sources (ja)"...
## "COVID-19 pandemic templates"],"wgPageContentLanguage":"en","wgPageContentMod...
## "Q87325019","wgGENewcomerTasksGuidanceEnabled":true,"wgGEAskQuestionEnabled":...
## ...

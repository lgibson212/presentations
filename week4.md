# What are the advantages and disadvantages of using a MVC model?
![mvc](https://i.stack.imgur.com/B19Ea.png)
![mvc](https://developer.chrome.com/static/images/mvc.png)

**Model** manages data
**View** manages what is displayed to user
**Controller** messenger btwn model and view
- *separates/isolates* the front end (what user sees) from the back end (what developer sees)

**Advantages**
- decoupling would allow more *modular* use of the models section
- simultaneous/parallel development of core logic and user-interface logic
- structure makes it easy to maintain
- more straight forward testing 

**Disadvantages**
- decoupling can lead to the delay of updating laterally - updating one requires updating another
- separation is too complicated for smaller applications
- not as relevant for web applications and modern UIs
 (developed in the 70s)


There are a few variations of the MVC design pattern such as MVP (Model–View–Presenter) and MVVP(Model–View–ViewModel). 


References:
- https://developer.chrome.com/apps/app_frameworks
- https://addyosmani.com/resources/essentialjsdesignpatterns/book/#detailmvc
- https://www.tutorialspoint.com/struts_2/basic_mvc_architecture.htm
- https://www.interserver.net/tips/kb/mvc-advantages-disadvantages-mvc/



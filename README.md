# 30 January update:
### 0.(still needs to run docker database and main.java separately)
### 1.updated package structure. now it has a service package. 
Controller(http mappings), business logic(service), models(entites and tables) are now three separated parts. Alse, business logic codes are now divided into more small functions. 
### 2.updated the whole test system. (tests are using h2 database which is open at localhost:8081)
### 3.added DeleteMapping and SearchMapping.


<br/>
<br/>
<br/>


# 25 January update:
### 0.(still needs to run docker database and main.java separately)
### 1.updated status code and folder structure


<br/>
<br/>
<br/>



# 21 January update:

### 0.(now needs to run docker database and main.java separately)
### 1.added a foreign key to the entity
### 2.now using enum
### 3.updated exception
### 4.realisation of business logic remains unchanged. how to make better use of stream()? 



<br/>
<br/>
<br/>



# 18 January update:
### How to run:
In the terminal, go to the directory of postgres.yaml, then $ docker-compose -f postgres.yaml up 

### 1.using flyway migration for data initialization 
### 2.no more use of gson. now it uses two model classes: BreakdownResult and LotCodeWithComponents
### 3.no more use of examplematcher. 
### 4.now tells the user whether he gets the wrong search_type or the wrong lotcode by using exception message
### 5.tried to use stream for business logic but failed 

<br/>
<br/>
<br/>






# old:
## How to run:
# 1. 
In the terminal, go to the directory of postgres.yaml, then $ docker-compose -f postgres.yaml up 

The database should now be open at port 5433. the database needs yet to be initialized. 

Now it only has the dafault database and no tables.
# 2. 
In Intelli J, run the main application class "WineBreakdownApiApplication". 

The initialization function will create two tables in the database named 'wine_lots'. 

It will also upload three lotcodes together with all their information integrated into the database. It extracts information from 3 json files located in the folder "/init data" and then uses java HttpRequest to post them to localhost:8080/api/post. 

# about the database:
The database has two tables. 

The table 'wine_lot_codes' has all the lotcodes and their basic information. 

The table 'wine_component' stores the information of components from all lotcdes, which are used to produce the query results.


# functions of the application:
the application has two functions:
# 1. 
 you can post the json file containing the lotcode and its relevant information to localhost:8080/api/post. The two tables will be updated accordingly. 
# 2. 
●	/api/breakdown/year/{lotCode} - breakdown of TOTAL percentage by year

●	/api/breakdown/variety/{lotCode} - breakdown of TOTAL percentage by variety

●	/api/breakdown/region/{lotCode} - breakdown of TOTAL percentage by region

●	/api/breakdown/year-variety/{lotCode} - breakdown of TOTAL percentage by year + variety combination


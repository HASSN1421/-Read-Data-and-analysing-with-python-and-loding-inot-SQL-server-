# Project Title



# Read Data and analysing with python and loding inot SQL server  


## project description

 


-Read CSV file 
- The CSV file (Data Science Job Salaries Dataset)
 -Analysis Data With python 

- with use pandas library (Put data in a frame,explore data ,add columns,replace values, change column name ,remove column )
-Loding the data into SQL server 

- With use pyodbc and sqlalchemy librarys connect to the sql server and loding the data into database


 




 ### Steps followed 

 - Step 1 : Read the data and explore data

      
         
                   #installing pandas data manipulation and analysis
                   !pip install pandas 
                   ---------------------------
                   import pandas as pd
                   #read csv file with pandas 
                   ds_df=pd.read_csv(r'ds_salaries.csv')
                   ds_df.head(4)
                   -----------------------------
                   #show the laast 5 rows from the table 
                   ds_df.tail()








   ![1-1](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/7daff3f1-d7f4-4d2a-b02b-5f236fed42b6)


         
                  
             #show the columns 
             ds_df.columns
             ----------------------
             #show the columns data tyoe 
             ds_df.dtypes
             -------------------
             #total the columns and rows 
             ds_df.shape 
             ----------------------------
             #show the max value 
             ds_df['salary_in_usd'].max()


  
  
    ![1-2](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/5b65ade6-ec96-474e-b2a6-0ace048d145e)


          
                   
        #how vlaues is null 
        ds_df.isnull().sum()
        ---------------------------
        #show unique values and print it 
        print('employment_type is',ds_df['employment_type'].unique())
        print('experience_level is',ds_df['experience_level'].unique())
        print('company_size is',ds_df['company_size'].unique())
        ----------------------------------

     ![1-3](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/13a75993-8dd0-497e-9655-a8acad82da40)

 - Step 2 :Add columns and change column data type




       #creat new column his name salary in SR  
       ds_df['salary in SR']=ds_df['salary_in_usd']*3.75
       ds_df.head()
       ----------------------------------
       #show the salary in SR  column SR data type 
       ds_df['salary in SR'].dtype
       ----------------------------- 
       #changing salary in SR data type 
       ds_df['salary in SR']=ds_df['salary in SR'].astype(int)
       ds_df['salary in SR'].dtype
       ------------------------------------

   ![2-1](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/477ffda5-e208-4641-8af5-6eb1e92ed75e)





          #show the max and min values 
          max=ds_df['salary in SR'].max()
          min=ds_df['salary in SR'].min()
          print('The max value ',max)
          print('The min value ',min)
          ----------------------
          #creat new column his name salary in month
          ds_df['salary in month ']=ds_df['salary in SR']/12
          ds_df.head() 
   ![2-2](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/0b1a75e3-551d-40c9-9f28-efcaa54ff110)


   
 - Step 3 : Replace value and remove columns





       #replace values 
       ds_df['company_size'].replace({'L': 'large','S': 'small','M':'Medium'} ,inplace=True)
       ds_df['company_size']

 ![3-1](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/cfbeebac-7aa3-4caa-b23f-a17127dd1c04)



        #remove columns from table 
        ds_df.drop(columns=['salary''salary_currency''remote_ratio'] ,inplace=True)
…             
              
        

 

  



- Step 4 : Loding into SQL server 




          #install pyodbc provides access to ODBC (Open Database Connectivity) databases. 
          !pip install pyodbc
          -------------------------
          #install sqlalchemy and impotr it( provides a flexible and efficient way to work with databases.) 
          #creat connect with SQL server(AAZ\SQLEXPRESS:server name ,lod=database name )          ds_df.to_sql('work_year',con=con,index=False,if_exists='replace') 
   ![4-1](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/d21e2f87-a831-448c-91b5-0a7d61c53ac7)




      #checking in sql serverserver 

   ![4-1-1](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/2db66d02-e511-4530-8d47-59bb85ac9e97)




           #creat new column his name new colimn
           ds_df['new colimn']=ds_df['salary in SR']/20
           ds_df.head()


   ![4-2](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/3d1de72b-9284-4d7d-88c6-6e1f98c05ade)




        #checking in sql server and rename the database and add index column
   ![last](https://github.com/user-attachments/assets/577ebd7f-4d89-40c0-8cfa-2d46e3bfbe1b)




   ![4-2-2](https://github.com/HASSN1421/-Read-Data-and-analysing-with-python-and-loding-inot-SQL-server-/assets/162873878/da6143b5-f367-40ee-9ed4-adad71636522)






 



















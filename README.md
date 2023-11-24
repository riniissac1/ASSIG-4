YOUTUBE CHANNEL ANALYSIS

Getting Started
Prerequisites
Ensure you have the following installed:

Anaconda
Jupiter Notebook
MYSQL Workbench
Installing
Run the jupiter notebook and and include follwing library. these library will allow the user to use the functions in the jupiter notebook.

import pandas as pd
import pandas as pd
from sqlalchemy import create_engine
import pymysql
now to connect the python with the database int the mysql use the following command. The command pip install pymysql installs the pymysql Python package, enabling communication with MySQL databases through Python scripts.

pip install pymysql
The create_engine command establishes a connection to a MySQL database named "assignment4" hosted on the local machine, using the username "usert" and password "password."

# create engine
engine = create_engine('mysql+pymysql://usert:password@localhost/assignment4')
The conn = engine.connect() command establishes a connection (conn) to a database using the SQLAlchemy engine (engine).

# create engine
conn = engine.connect()
Now we are all set to do the youtube channel analysis
you can downlaod the dataset from here https://github.com/rehalarjun/DATA1202/blob/main/youtube_dataset.csv

Running the analysis
to run the analyisi first downlaod the assignemt4.ipynb file in your local machine and then start the jupiter notebook. image

now go the the file section of the jupiter notebook and locate the assignemt4.ipynb and then click on it image

when you click on it you will have this kind of interface image

now srat running the command by just selecting the cell and hitting on the run button on the above rebin.

make sure to change the path of the file to where you have downlaoded the dataeset image

lastly change the credential according to what the user have set on ones mysql workbench to connect to it image

Breakdown of Tests
Calculate Channel Distribution:

Description: Calculates the distribution of channel types from the loaded dataset.
Command:
channel_distribution_result = calculate_channel_distribution(data)
print(channel_distribution_result)
Load Top 1000 Data:

Description: Loads the top 1000 records from the sorted dataset into a CSV file.
Command:
top_1000_data = load_data_top_1000(data)
Read and Verify Loaded Data:

Description: Reads the CSV file containing the top 1000 records and displays the loaded DataFrame.
Command:
data2 = pd.read_csv('top_1000_channels.csv')
data2.head()
Database Connection and Query:

Description: Creates a connection to a MySQL database using SQLAlchemy and reads a simple query into a DataFrame.
Command:
df = pd.read_sql("SELECT * FROM assignment4.youtube_dataset", conn)
print(df.head())
Write Data to MySQL Table:

Description: Writes the loaded DataFrame to a MySQL table.
Command:
data2.to_sql(table_name, con=engine, if_exists='replace', index=False)
Note: Ensure that the MySQL server is running and the database and table names match your actual setup.

Feel free to modify the descriptions and commands as needed for your specific project.

Deployment
To deploy this script, make sure you have a MySQL database set up and modify the connection details in the script. Then, run the script to load the data into the database.

Author
Rini Issac

Lisence
This project is licensed under the MIT License - see the LICENSE.md file for details.

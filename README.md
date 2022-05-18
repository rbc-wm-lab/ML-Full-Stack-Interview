# ML-Full-Stack-Interview
Welcome to the full stack developer interview. In this interview, there will be three tasks. 

- **Task 1**: Deploy and Run a Jupyter Notebook Server
- **Task 2**: Data Analysis
- **Task 3**: Presenting Data
  - Option 1: Python Data Visualisation
  - Option 2: Webpage Deployment

> We believe that solving problems by searching online information is an important skill that you will be commonly used in your entire career life. Therefore, **you are free to google search** for any technical instructions, documentations and any other open resources during this interview. 

## Task 0: Preparation

Before you start, please check your public IP address and send it to the interviewer. This is needed to whitelist your public IP to grant access to our remote servers. Your data will be deleted immediately after the interview finishes. 

>You can do so by running ```curl ifconfig.me``` in your terminal or simply open [https://ifconfig.me/](https://ifconfig.me/ "ifconfig") in your web browser. 

## Task 1: Deploy and Run a Jupyter Notebook Server

In this task, you will need to set up a Jupyter Notebook on a remote server, and make sure all dependencies and requirements are satisfied. 

#### Server system
By default, you will be provided a Ubuntu operating system. Feel free to suggest any other OS you prefer. 

#### Login
The remote server’s public DNS is:

`ec2-3-69-50-110.eu-central-1.compute.amazonaws.com`

Username:

`ubuntu`

The private key for ssh is provided in this repository. The file name is:

`interview.pem`

You'll need to use `ssh` to connect to the remote server. You can use terminal (if you are using MacOS or Linux), powershell (if you are using Windows) or any other standalone ssh tools such as PuTTTY or WinSCP. 

#### Requirements
You need to set up an Jupyter Notebook server with secured login, so that end users are able to login in to your notebook server with a passcode through a web browser. 

By default, Python is the language to be used in the notebook server. However, you could also plug-in any other language kernels, such as Java, Scala, JS, etc. 

Apart from language it self, you should also set up a working environment for task B, C, and D. Ideally, you could use this notebook server as your IDE for future tasks. Have a look at the following tasks, and decide what packages you need.


## Task 2: Data Analysis

In this task, you will need to write a program to analyse world's billionaires data. 
Data are stored in the file `billionaires.csv`

In order to get this file on the remote server, you need to clone this repo to the remote server. 

#### Data explanation
The Forbes' Dataset comprises 2750 people whose net wealth equals to or exceeds one billion US Dollars.

Columns Descriptions:

1. Name: Name of the person or family.
2. Networth: Expressed in Billion USD.
3. Country
4. Source: main source from which the wealth is originated. 
5. Age
6. Residence: In the format of "City, State" or "City, Country".
7. Citizenship
8. Status: Marital status.
9. Childen: Number of children they have.
10. Education: Degree aquired and the educational institution. 
11. Self_made: (True/False) origin of wealth.
12. geometry

> Note that only some columns are used in this task. 

#### Data Sample


| Name                     | NetWorth | Country       | Source                 | Age | Residence               | Citizenship   | Status   | Children | Education                                                | Self_made | geometry                              |
| ------------------------ | -------- | ------------- | ---------------------- | --- | ----------------------- | ------------- | -------- | -------- | -------------------------------------------------------- | --------- | ------------------------------------- |
| Liang Wengen             | 14.1     | China         | construction equipment | 64  | Changsha, China         | China         | Married  | 1        | Bachelor of Arts/Science, Central South University       | TRUE      | POINT (112.9335861 28.2302056)        |
| Philippe Laffont         | 2.1      | United States | hedge fund             | 53  | New York, New York      | United States | Married  |          | Master of Science, Massachusetts Institute of Technology | TRUE      | POINT (-74.00601519999999 40.7127281) |
| Yao Kuizhang             | 1.6      | China         | beverages              | 56  | Hengshui, China         | China         |          |          |                                                          | TRUE      | POINT (115.6677229 37.7364305)        |
| Peng Yongdong            | 1.9      | China         | real estate            | 41  | Beijing, China          | China         |          |          |                                                          | TRUE      | POINT (116.3912757 39.906217)         |
| Jeffrey Gundlach         | 2.2      | United States | investments            | 62  | Los Angeles, California | United States | Divorced |          | Bachelor of Arts/Science, Dartmouth College              | TRUE      | POINT (-118.242766 34.0536909)        |
| Petro Poroshenko         | 1.6      | Ukraine       | confectionery          | 55  | Kiev, Ukraine           | Ukraine       | Married  | 4        | Bachelor of Arts/Science, Kiev State University          | TRUE      | POINT (30.5241361 50.4500336)         |
| Eva Maria Braun-Luedicke | 1.6      | Germany       | medical technology     | 34  | Melsungen, Germany      | Germany       |          |          |                                                          | FALSE     | POINT (9.5437136 51.1298048)          |
| Donald Newhouse          | 17.6     | United States | media                  | 91  | New York, New York      | United States | Widowed  | 3        | Drop Out, Syracuse University                            | FALSE     | POINT (-74.00601519999999 40.7127281) |
| Thomas Lee               | 2        | United States | private equity         | 77  | New York, New York      | United States | Married  | 5        | Bachelor of Arts/Science, Harvard University             | TRUE      | POINT (-74.00601519999999 40.7127281) |
| Kim Jung-woong           | 1.2      | South Korea   | cosmetics              | 46  | Seoul, South Korea      | South Korea   | Married  | 1        | Associate in Arts/Science, Daelim University             | TRUE      | POINT (126.9782914 37.5666791)        |


#### Your Task

1. Write a program to let user type in a column name, and then sort (either in ascending or descending order) all rows based on the input value.
2. Write a program to group all rows based on sector/industry (the "Source" column). Then generate a new table which contains only the top 3 wealthiest people in each sector/industry. 
3. Write a program to count the number of billionaires in each country (using either the "Country" or the "Citizenship" column). Output each country name along with the count. 

> Note that this file is encoded using 'utf-8' character set. You might need to specify this encoding when your program reads the file.


## Task 3 Presenting Data

In this task, you'll need to present the data you just analysed. You may choose one from the two options. 


### Option 1: Python Data Visualisation

In this task, you'll need to use a python visualisation library to display data. We recommend to use matplotlib or seaborn. 

#### Your Task

Use the result of the third subtask in task 2, i.e. counting the number of billionaires in each country. Generate a bar chart or a line chart to display the number of billionaires (y axis) against countries (x axis). 

- If you are using a bar chart, please order data based on the count in descending order. 

- If you are using a line chart, please order data based on country names in ascending order. 

### Option 2: Webpage Deployment

In this task, you'll need to host a web page to display data. We recommend to use any of the following architectures: 

- Apache
- Nginx
- Tomcat
- Node.js
- Flask
- Django

#### Your Task
Use the result of the third subtask in task 2, i.e. counting the number of billionaires in each country. Generate a table in your webpage. The table should contain two columns: country and count.

- If you are deploying a static web page, please export your result in python to a JSON file and use javascript (or any other web page scripting language) to read the file and generate a table. 

- If you are deploying a dynamic web page using Flask or Django, please make a template of the web page with holes and fill in the holes with data in Flask or Django. 


## Handbook

Here are some issues that you may encounter:

#### Permissions for '{key name}' are too open.

If you are running ssh on Windows, you might see the following error when you try to connect to the remote server:

```
C:\>ssh ubuntu@{DNS} -i {key name}
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions for '{key name}' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "{key name}": bad permissions
ubuntu@{DNS}: Permission denied (publickey).
```

##### Solution

[Stackoverflow Solution](https://superuser.com/questions/1296024/windows-ssh-permissions-for-private-key-are-too-open)

#### Unable to clone repo on the remote server.

If you are trying to download the dataset file but you are unable to clone this repo on the remote server, you may need to clone it to your own machine and use `scp` to transfer the file through ssh. 


# ML-Full-Stack-Interview
Welcome to the full stack developer interview. In this interview, there will be three tasks. 

* **Task 1**: Install Necessary Tech Stack on a Plain Server
* **Task 2**: Populate Database
* **Task 3**: Presenting Data


### 💡
> We believe that solving problems by searching for information online is an important skill you will use throughout your life as a software developer. Therefore, **you are free to Google search** for any technical documentation or any other open resources you may require during this interview. 

> Feel free to use any IDE, shell or any other tools if you want. We are not testing if you can use some tool that you have never used before.

We also prepared a [handbook](#handbook) in this document which discusses some commonly seen issues. 

## Task 0: Preparation

Before you start, please check your public IP address and send it to the interviewer. This is needed to whitelist your public IP to grant access to our remote servers. Your data will be deleted immediately after the interview finishes. 

>You can do so by running ```curl ifconfig.me``` in your terminal or simply open [https://ifconfig.me/](https://ifconfig.me/ "ifconfig") in your web browser. 

## Task 1: Install Necessary Tech Stack on a Plain Server

In this task, you will need to set up all necessary tools on a remote server, and make sure all dependencies and requirements are satisfied.
You'll need to install the following tools:
* Any SQL database
* Any web server (e.g. Nginx, Apache, Node.js, Flask, etc.)
* Any programming language to populate the database
* Any other tools needed

#### Server system
By default, you will be provided a Ubuntu operating system on the remote instance. If you prefer another flavour of Linux, let us know.

#### Login
The remote server’s public IP address is one of the following:

* `*.*.*.*`
* `*.*.*.*`

### 💡
> Please note that the server's public IP above is a **static** IP address, so you are free to access it via your `~/.ssh/config`if you wish.

Your username for the instance will be `ubuntu` (if using Ubuntu).

The private key for ssh access to the instance is provided in this repository. The file name is `interview.pem`.

You'll need to use `ssh` to connect to the remote server. You can use terminal (if you are using MacOS or Linux), powershell or WSL (if you are using Windows) or any other standalone ssh tools such as PuTTY or WinSCP to move data between your local machine and the remote. 


## Task 2: Populate Database

In this task, you will need to write a program to import the world's billionaires' data into the database you set up in Task 1. 
The data is stored in the file `billionaires.csv`

In order to get this file on the remote server, you need to clone this repo to the remote server. 

#### Data explanation
The Forbes Dataset comprises 2,750 people whose net worth equals or exceeds 1 billion US Dollars.

Columns Descriptions:

1. Name: Name of the person or family name
2. Networth: Expressed in billions of USD
3. Country
4. Source: main source from which the wealth originated
5. Age
6. Residence: In the format of `City, State` or `City, Country`
7. Citizenship
8. Status: Marital status
9. Children: Number of children
10. Education: Educational institution degree was acquired from
11. Self_made: (True/False) origin of wealth
12. Geolocation: Location of primary residence

> Note that only some columns are used in this task. 

#### Data Sample


| Name                     | NetWorth | Country       | Source                 | Age | Residence               | Citizenship   | Status   | Children | Education                                                | Self_made | Geolocation                              |
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


#### Your Tasks

1. Read the columns descriptions and the sample data. Write a program to analyse the full data if needed.
2. Create three tables: **Person**, **Country** and **City**. Note that country data appear in *Country*, *Residence* and *Citizenship* columns, and city data appear in *Residence* column.
   Design proper database schema. Add a primary key to all tables. You may choose among incremental numbers, UUID or original data as the primary key. Create foreign keys for proper columns. 
3. Write a program to load the csv file and import into the tables. 
### 💡 Keep in mind
* This file is encoded using 'utf-8' character set. You may need to specify this encoding when reading in the file.
* Code readability matters! Bonus points for formatting/linting your code in a way that makes it more readable to other developers.

## Task 3: Presenting Data

In this task, you'll host a web page to display the data to a non-technical audience. We recommend using any of the following frameworks: 

#### Your Task
Counting the number of billionaires in each country, and the average networth of billionaires in each country. Generate a table in your webpage. The table should contain three columns: country, count and avg networth.

- If you are deploying a *static* web page, please export your result from Python to a JSON file and use JavaScript (or any other web-friendly language) to read the file and generate a table. 

- If you are deploying a *dynamic* web page using PHP, Flask, Django, etc., please make a template of the web page with holes and fill in the holes with data.


## Handbook

Below, we list some issues that you may encounter:

### Permissions for `{key_name}` are too open

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

If you are running ssh on MacOS or Linux, you might see the following error when you try to connect to the remote server:

```
$:ssh ubuntu@{DNS} -i {key name}
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for '{key name}' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "{key name}": bad permissions
Permission denied (publickey).
```

As in many other situations, you are free to look at StackOverflow to obtain answers.

* [Example Stackoverflow Solution 1](https://superuser.com/questions/1296024/windows-ssh-permissions-for-private-key-are-too-open)
* [Example Stackoverflow Solution 2](https://stackoverflow.com/questions/9270734/ssh-permissions-are-too-open-error)

### Unable to clone repo on the remote server

If you are trying to download the dataset file but you are unable to clone this repo on the remote server due to ssh permission issues, you may need to clone it to your own machine and use `scp` to transfer the file through ssh. 

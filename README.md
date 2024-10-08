﻿# Simple crud in ASP.Net 6 using Dapper to interact with SQL Server database
<p>this is a simple example implementation of Dapper using netcore 6, hope you enjoy it!</p>
<p>NuGet Package requirements :</p>
<ul>
  <li>Dapper 2.1.15</li>
  <li>System.Data.SqlClient 6.0.16</li>
</ul>

<p>General Information</p>
<ul>
  <li>Theme installed: AdminLTE 3.2.0</li>
  <li>Database: Microsoft SQL Server</li>
</ul>

<p>Open query editor connected to your database, copy this query below then execute each query</p>
<b>Book table<b>
	
```SQL
CREATE TABLE [dbo].[book](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[title] [text] NULL,
	[author] [varchar](150) NULL,
	[publisher] [varchar](150) NULL,
	[year] [int] NULL,
	[ref_genre_id] [int] NULL
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
```
<br>

<b>Genre reference table</b>
```SQL
CREATE TABLE [dbo].[ref_genre](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[genre] [varchar](50) NULL
) ON [PRIMARY]
```
<b>Member table</b>
```SQL
CREATE TABLE [dbo].[member](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[name] [varchar](50) NULL,
	[member_code] [varchar](50) NULL
) ON [PRIMARY]
```
<br>
<b>Visitor table</b>
```SQL
CREATE TABLE [dbo].[visitor](
	[id] [int] IDENTITY(1,1) NOT NULL,
	[member_id] [int] NOT NULL,
	[visiting_date] [datetime] NULL
) ON [PRIMARY]
```
<br>
<b>Manually seeding the database</b>

```SQL
INSERT INTO ref_genre (genre) VALUES
('Fantasy'),('Science Fiction'), ('Adventure'),
('Romance'),('Horor'), ('Biography');

INSERT INTO member (member_code, name) VALUES
('Andy', '000001'),('Ani', '000002'),('Patrick', '000003');
```
<p>Congratulations! This is the final step. Clone the repository, install Nuget Package requirement then configure the database connection. Then, run it!</p>

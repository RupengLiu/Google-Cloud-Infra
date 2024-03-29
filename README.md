# Google-Cloud-Infra

## Table of contents
* [About Cloud Computing in Google](#about-cloud-computing-in-google)
* [About Kurbenetes](#about-kurbenetes)
* [About Security](#about-security)
* [Identity and Access Management](#identity-and-access-management)
* [Virtual Machines and Network in the cloud](#virtual-machine-and-network-in-the-cloud)
* [Storage in the cloud](#storage-in-the-cloud)
* [Container](#container)
* [Kubernetes](#kubernetes)
* [App Engine](#app-engine)
* [About Data Tools](#about-data-tools)


### About Cloud Computing in Google
![image](https://user-images.githubusercontent.com/29927264/62795886-9e90fa80-ba8c-11e9-8a23-dee3b2f387c1.png)
![image](https://user-images.githubusercontent.com/29927264/62796697-afdb0680-ba8e-11e9-951c-140d324f921a.png)
### About Kurbenetes
![image](https://user-images.githubusercontent.com/29927264/62805978-626a9380-baa6-11e9-9d20-f005b4364935.png)
![image](https://user-images.githubusercontent.com/29927264/62806437-b164f880-baa7-11e9-88cd-ddb1b2b8ac02.png)
![image](https://user-images.githubusercontent.com/29927264/62806494-dfe2d380-baa7-11e9-9903-8ffb8e847b8b.png)
![image](https://user-images.githubusercontent.com/29927264/62806798-9fd02080-baa8-11e9-85e8-3463afeaef18.png)
![image](https://user-images.githubusercontent.com/29927264/62806856-c42bfd00-baa8-11e9-9b4f-f39d6bbb9ee8.png)
### About Security
![image](https://user-images.githubusercontent.com/29927264/62809125-ec1e5f00-baae-11e9-89aa-a93c29672300.png)
### About IaaS/Paas/SaaS
![image](https://user-images.githubusercontent.com/29927264/62809400-b5951400-baaf-11e9-978f-38ab8d39685d.png)
### Identity and Access Management
![image](https://user-images.githubusercontent.com/29927264/62809791-d0b45380-bab0-11e9-8d6d-94f90cf2615b.png)
![image](https://user-images.githubusercontent.com/29927264/62809981-5a642100-bab1-11e9-8487-1c05549424c1.png)
![image](https://user-images.githubusercontent.com/29927264/62810173-fd1c9f80-bab1-11e9-941c-588c088fa215.png)
### Virtual Machines and Network in the cloud
![image](https://user-images.githubusercontent.com/29927264/62811569-03614a80-bab7-11e9-8adc-22559a39a829.png)
### Storage in the cloud
![image](https://user-images.githubusercontent.com/29927264/62811974-a797c100-bab8-11e9-9907-9e5d74932f69.png)
* It's not file storage, it's not the same as block storage in which your operating system manage your data as chunk of disks. It's stored as arbitrary bunch of bytes with a unique key, these unique keys are in the form of URLS, which interates nicely with web. 
* It's a fully managed, scalable services. It's no a file system. 
* It always encrypte your data on the server side 
* Changing data will not overwrite the original one, the object in the storage is imutable, it create a new chunk of data and delete the original one
![image](https://user-images.githubusercontent.com/29927264/62812515-e9296b80-baba-11e9-9195-56abac44c93d.png)
* Multi-regional and regional are high performance object storage, whereas nearline and coldline are backup and archival storage
* Multi-regional storage store data in different region and store frequent accessed data, interacrive workloads, or data that's part of mobile and gaming applications.
* People use regional storage to store data close to their compute engine virtual machine or Kubernetes Engine clusters. That gives better performance for data intensive computations. 
* Nearline storage is a low cost, highly durable service for storing infrequently accessed data. 
* Coldline storage is a very low cost, highly durable service for data archiving, online backup, and disaster recovery. Low avalability, higher per operation costs. 
![image](https://user-images.githubusercontent.com/29927264/62813375-3e677c00-babf-11e9-93c2-c1c9e7648552.png)
#### Cloud SQL
![image](https://user-images.githubusercontent.com/29927264/62813120-f2680780-babd-11e9-9c6a-ff54135002c0.png)
* provide several replica services like read, failover, and external replicas. This means that if an outage occurs, cloud sql can replicate data between multiple zones with automatic failover. 
* automatic failover: Automatic failover is a resource that allows a system administrator to automatically switch data handling to a standby system in the event of system compromise. Here, automatic describes the failover process. By definition, most failover processes are programmed to operate automatically.
* help you back up your data with either on demand or scheduled backups. It can also scale both vertically by changing the machines type and horizontally via read replicas.
![image](https://user-images.githubusercontent.com/29927264/62815138-d61e9780-baca-11e9-8299-62ec3d7e6478.png)
#### Big Table
![image](https://user-images.githubusercontent.com/29927264/62813153-19263e00-babe-11e9-8de5-d7e413f9a694.png)
* Cloud big table is google's NoSql, big data databse services
* It's ideal for data that has single lookup key. Ideal for storing large amounts of data with very low latency. It supports high through put, both read and write, so it's a great choice for both operational and analytical applications, including internet of things, user analytics and financial data analysis. 
* Cloud bigtable is offered through the same open source API as Hbase, which is the native database for the Apach Hadoop project, enable portability(可移植性) between HBase and Bigtable
* Compared Bigtable with Hbase: bigtable has scalability (tough for Hbase to scale per second), increase machine count without downtime.
* All data in Bigtable is encrypted in both inflight and at rest. You can even use IAM permissions to control who has access to Bigtable data. 
* Bigtable is actually the same database that powers many google's core services, including search, analytics, maps and gmail.
#### Big Query
![image](https://user-images.githubusercontent.com/29927264/62813256-9f428480-babe-11e9-9b6f-07bfe835f845.png)
* mainly built for data analysis, won't use it as datastore for an app
#### Cloud Spanner
![image](https://user-images.githubusercontent.com/29927264/62813361-27288e80-babf-11e9-88f3-025d6de37ac5.png)
* if cloud sql doesn't fit your requirement bc you need more horizontal scalability, consider using cloud spanner. It offers transactional consistency at a global scale, schemas, sql and automatic synchronous replication for high availability, and it can provide petabyte of capacity.
* Use when have outgrown any relational database, are sharding your databases for throughput high performance, need transactional consistency, global data and strong consistency, or just want to consolidate your database. (financial applications and inventory applications) 
#### Cloud Datastore 
* is a horizontally scalable NoSql database, designed for application backends. 
* to store structured data from app engine apps. 
* automatically handle sharding, replication, providing you with a highly durable and available database that scales automatically to handle load. Unlike bigtable, it also offers transactions that affect multiple database rows and it lets you do sql-like queries

![image](https://user-images.githubusercontent.com/29927264/62815385-3ca4b500-bacd-11e9-87d6-4e4dceaca6dc.png)
* Datastore is the best for semi-structured application data that is used in App Engine's applications. 
* Bigtable is best for analytical data with heavy/write events like ad tech, financial or loT data.
* Cloud Storage is best for structured and unstructrued binary or object data like images, large media files, and backups.
* Cloud Sql is best for web frameworks and existing applications like storing user credentials and customer orders.
* Cloud spanner is best for large scale database applications that are larger than 2 TB (finacial trading)

### Container
![image](https://user-images.githubusercontent.com/29927264/62880581-97632a00-bce2-11e9-887d-d5583dbab6ea.png)
![image](https://user-images.githubusercontent.com/29927264/62881003-97175e80-bce3-11e9-8404-469dd3c863e7.png)
![image](https://user-images.githubusercontent.com/29927264/62881547-df834c00-bce4-11e9-8dd0-c587aa29404e.png)
![image](https://user-images.githubusercontent.com/29927264/62881702-3557f400-bce5-11e9-9dc2-8e868e9c8c21.png)
* When using IaaS, as demand for your application increases, you have to copy an entire VM and boot the guest OS for each instance of your app, which can be slow and costly. With app engine, you can get access to programming services, so all you do is write your code in self-contained workloads that use these services and include any dependent libraries. As demand for you app increases, the platform scales your app seamlessly and independently by workload and infrustructure. This scale rapidly, but you won't be able to fine tune the underlying architecture to save cost. That's where containers come in. The idea of a container is to give you the independently scalability of workloads and an abstraction layer of the OS and hardware. What you get is an invisible box around your code and its dependencies with limited access to your own partition of the file system and hardware. It only requires a few system calls to create and starts as quickly as a process. All you need on each host is an OS kernel that supports container and container runtime. In essence, you're virtualizing the OS, it scales like paths, but gives you the nearly same flexibility as IaaS. With this abstraction, your code is ultra-portable and you can treat the OS and hardware as a black box. So you can go from development to staging to production, or from our laptop to the cloud without changing or rebuild anything. If you want to scale for example, a web server, you can do it in a second or hundreds of them, depending on the size of your workload, on a single host. Now, that's a simple exmaple of scaling one container, running a whole application on a single host. You likely want to build your application using lots of containers, each performing their own function like microservices. If you build them like this, and connect them with network connections, you can make them modular, deploy easily, and scale independently across a group of hosts. And the host can scale up or down and start and stop the containers on demand, as demand for your application changes or as host fails. A tool that helps you do this well is Kubernetes. Kubernetes makes it easy to orchestrate many containers on many hosts, scale them as microservices, and deploy rollouts and rollbacks.


### Kubernetes
* Abstract containers at high level so you can better manage and scale your applications.
![image](https://user-images.githubusercontent.com/29927264/62885382-971c5c00-bced-11e9-9748-b97ea481a6a3.png)


### App Engine
![image](https://user-images.githubusercontent.com/29927264/62885815-ab148d80-bcee-11e9-8a36-f588ff9f2639.png)
* Especially suited for building scalable web applications and mobile backends
#### App Engine Standard Env
* Offers simpler deployment experience than the flexible environment and fine-grained auto scale and offer free daily usage quota. 
* SDKs for development, testing and deployment
* has specific version of Java, Python, PHP, and Go
![image](https://user-images.githubusercontent.com/29927264/62886326-e2d00500-bcef-11e9-9856-d4ec7b83b348.png)
![image](https://user-images.githubusercontent.com/29927264/62886649-638f0100-bcf0-11e9-8f16-53e3140ff4ac.png)
![image](https://user-images.githubusercontent.com/29927264/62886762-a81a9c80-bcf0-11e9-8793-d6d1cbc1e695.png)

#### App Engine Flexible
![image](https://user-images.githubusercontent.com/29927264/62886847-d4361d80-bcf0-11e9-9586-3568399f820c.png)
![image](https://user-images.githubusercontent.com/29927264/62887032-4575d080-bcf1-11e9-91bf-8544ba0066a0.png)
![image](https://user-images.githubusercontent.com/29927264/62887136-879f1200-bcf1-11e9-883b-8c4407e33587.png)
![image](https://user-images.githubusercontent.com/29927264/62888512-4d833f80-bcf4-11e9-871a-4d51f55f347a.png)
![image](https://user-images.githubusercontent.com/29927264/62888578-70155880-bcf4-11e9-9d57-acc84f8a6c5c.png)
![image](https://user-images.githubusercontent.com/29927264/62888745-caaeb480-bcf4-11e9-80c7-1486fe1675c3.png)

### About Data Tools
![image](https://user-images.githubusercontent.com/29927264/62889397-2b8abc80-bcf6-11e9-9ae9-4e0c42c727ff.png)
#### Cloud Dataproc
![image](https://user-images.githubusercontent.com/29927264/62893378-4d3c7180-bcff-11e9-8cd9-fb470e6c4e30.png)
![image](https://user-images.githubusercontent.com/29927264/62893507-a906fa80-bcff-11e9-9d93-3b4e2dd878fc.png)
#### Cloud Dataflow 
![image](https://user-images.githubusercontent.com/29927264/62894405-7e1da600-bd01-11e9-9453-77d320de53b3.png)
![image](https://user-images.githubusercontent.com/29927264/62894672-0e5beb00-bd02-11e9-960a-96982b569da6.png)
![image](https://user-images.githubusercontent.com/29927264/62894793-524ef000-bd02-11e9-953c-47e79fea288e.png)
![image](https://user-images.githubusercontent.com/29927264/62894858-7d394400-bd02-11e9-83a1-bb487110cc3e.png)
![image](https://user-images.githubusercontent.com/29927264/62894910-a1952080-bd02-11e9-9ab5-7839ce5a8075.png)
#### Big Query
![image](https://user-images.githubusercontent.com/29927264/62895042-e1f49e80-bd02-11e9-9ec8-29ec795e298f.png)
* No cluster maintenance is required.
#### Cloud Pub/Sub 
![image](https://user-images.githubusercontent.com/29927264/62895319-7c54e200-bd03-11e9-9fd0-4ecb75005486.png)
* Building block for data ingesting in Dataflow, internet of Things (loT), marketing analytics
* Foundation for Dataflow streaming
* Push notifications for cloud-based applications
* Connect applications across Google Cloud Platform (Push/Pull between Compute Engine and App Engine)
#### Cloud Datalab 
![image](https://user-images.githubusercontent.com/29927264/62896021-05b8e400-bd05-11e9-81e4-e63d6dec51ba.png)
![image](https://user-images.githubusercontent.com/29927264/62896576-32213000-bd06-11e9-9de8-ef92375d2071.png)
![image](https://user-images.githubusercontent.com/29927264/62896649-554bdf80-bd06-11e9-8826-939d7f2565f2.png)
#### TensorFlow
![image](https://user-images.githubusercontent.com/29927264/62896810-a360e300-bd06-11e9-89cd-74cd2106995e.png)
![image](https://user-images.githubusercontent.com/29927264/62897020-25e9a280-bd07-11e9-9efc-d3991bfb0c79.png)


## [Back](#table-of-contents)





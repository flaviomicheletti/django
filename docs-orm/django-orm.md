# Django ORM

## Main

The 80/20 principle, also known as the Pareto principle, suggests that 
roughly 80% of the results come from 20% of the efforts. Applying this 
principle to learning Django ORM, here are the most important aspects that 
will help you understand the majority of the topic: 

1. **Models:** Django ORM revolves around models, which are Python classes that 
represent database tables. Focus on understanding how to define models, 
specify fields (such as CharField, IntegerField, ForeignKey, etc.), and 
define relationships between models (OneToOneField, ForeignKey, 
ManyToManyField). 

2. **QuerySets:** QuerySets are the primary way to retrieve data from the 
database using Django ORM. Learn about various query methods and operators 
available on QuerySets, such as filter(), exclude(), get(), all(), values(), 
annotate(), and aggregate(). Understanding how to chain methods together to 
build complex queries is crucial. 

3. **CRUD Operations:** Django ORM provides a convenient way to perform Create, 
Read, Update, and Delete (CRUD) operations on database records. Learn how to 
use methods like create(), save(), update(), and delete() to manipulate 
records in the database using models and QuerySets. 

4. **Migrations:** Django ORM includes a built-in migration system that allows 
you to manage database schema changes over time. Learn how to create and 
apply migrations to keep your database schema in sync with your model 
changes. 

5. **Relationships:** Understanding how to define and work with relationships 
between models is essential. Learn about ForeignKey (one-to-many), 
OneToOneField (one-to-one), and ManyToManyField (many-to-many) relationships. 
Explore related concepts like related_name, on_delete behavior, and querying 
related objects. 

6. **Aggregation and Annotation:** Django ORM provides powerful aggregation and 
annotation functions to perform calculations and aggregations on QuerySets. 
Familiarize yourself with functions like count(), sum(), average(), 
annotate(), and aggregate() to perform complex calculations on your data. 

7. **Optimization and Performance:** As your application grows, it's crucial to 
optimize database queries for performance. Learn about techniques like 
select_related(), prefetch_related(), and index optimization to reduce 
database hits and improve query performance. 

8. **Transactions and Atomicity:** Django ORM supports transactions, which ensure 
that a group of database operations either succeeds or fails together. 
Understand how to use transactions to maintain data integrity and handle 
atomic operations. 

By focusing on these key aspects, you'll be able to grasp the fundamental 
concepts and techniques of Django ORM, enabling you to work with models, 
perform queries, manipulate data, handle relationships, and optimize 
performance effectively. Remember, as you gain more experience, you can delve 
into the remaining 20% of the details to further enhance your knowledge and 
skills.


## Plan of study

Here's a learning plan to help you become proficient in Django ORM, assuming 
you already have a good understanding of Python: 

1. **Get Familiar with Django**: If you haven't worked with Django before, 
start by familiarizing yourself with the Django framework as a whole. 
Understand its architecture, file structure, and core concepts such as 
models, views, templates, and URL routing. You can follow the official Django 
tutorial (https://docs.djangoproject.com/en/stable/intro/tutorial01/) to 
build a basic Django project. 

2. **Study Relational Databases**: Since Django ORM primarily works with 
relational databases, it's important to have a solid understanding of 
relational database concepts. Learn about tables, columns, primary keys, 
foreign keys, and relationships between tables. Familiarize yourself with SQL 
queries, joins, and basic database design principles. 

3. **Dive into Django ORM**: Start by understanding Django's Object-
Relational Mapping (ORM) and its advantages. Begin with the Django ORM 
documentation (https://docs.djangoproject.com/en/stable/topics/db/models/) to 
learn about models, fields, and relationships. Experiment with creating 
models, defining fields, and understanding the different field types 
available in Django. 

4. **CRUD Operations**: Practice performing Create, Read, Update, and Delete (
CRUD) operations using Django ORM. Create sample models, save objects to the 
database, retrieve data using queries, update records, and delete records. 
Work through examples and exercises to solidify your understanding of these 
operations. 

5. **QuerySets**: Dive deeper into QuerySets, the primary way to retrieve 
data from the database. Explore various querying techniques such as 
filtering, excluding, ordering, limiting, and pagination. Learn about complex 
queries, chaining methods, and utilizing query operators. Practice writing 
different types of queries to become comfortable with querying data. 

6. **Model Relationships**: Focus on understanding and working with 
relationships between models. Study ForeignKey, OneToOneField, and 
ManyToManyField relationships. Learn how to define and query related objects, 
handle cascading deletes, and manage reverse relationships. Practice building 
models with different types of relationships. 

7. **Migrations**: Study Django's migration system to manage database schema 
changes. Learn how to create and apply migrations, handle schema alterations, 
and work with advanced migration features like data migrations, dependency 
management, and squashing migrations. Practice creating and applying 
migrations for model changes. 

8. **Performance Optimization**: Dive into techniques for optimizing Django 
ORM queries and improving performance. Learn about query optimization, 
database indexing, caching, and using tools like Django Debug Toolbar. 
Understand when and how to use select_related(), prefetch_related(), and 
other optimization methods. 

9. **Transactions and Atomicity**: Study transactions in Django ORM to 
maintain data integrity and handle atomic operations. Learn how to use 
transactions effectively, handle exceptions, and ensure data consistency. 
Practice using transactions in scenarios where multiple database operations 
need to be atomic. 

10. **Advanced Concepts**: Explore advanced Django ORM concepts based on your 
specific project needs. This may include working with complex queries, 
aggregation and annotation, custom database functions, raw SQL queries, and 
using third-party Django packages for database interactions. 

Remember to combine theory with hands-on practice throughout the learning 
process. Work on coding exercises, tackle challenges, and build projects that 
leverage Django ORM. Additionally, referring to the official Django 
documentation and exploring external resources like books, tutorials, and 
online courses can provide valuable insights and further enhance your 
understanding. Happy learning and mastering Django ORM!

## Does Django ORM use SQLAlchemy?

Differences – SQL Alchemy vs Django

Main difference is that Django ORM uses the “active record implementation”, 
and SQL Alchemy uses “data mapper implementation”. It means that Django ORM 
cannot use our models for queries if every row is not linked with the overall 
model object. 

## Does Django ORM support MongoDB?

Django, the most popular Python web framework, is an ideal tool to build 
secure and easy-to-maintain applications using MongoDB. Using MongoDB with 
Django is advantageous because: Every second, more and more unstructured data 
is generated from various sources like chats, real-time streams, feeds, and 
surveys. 

Yes, Django ORM (Object-Relational Mapping) primarily supports relational 
databases like PostgreSQL, MySQL, SQLite, and Oracle. However, it does not 
natively support MongoDB, which is a NoSQL database. 

Django's ORM is designed to work with relational databases, utilizing SQL for 
data manipulation. MongoDB, on the other hand, is a document-oriented NoSQL 
database that does not use SQL. As a result, Django's ORM is not directly 
compatible with MongoDB. 

If you want to use MongoDB with Django, there are a couple of options 
available: 

1. Third-party packages: You can use third-party Django packages that provide 
integration with MongoDB. One popular package is "djongo," which allows you 
to use MongoDB as the underlying database for Django. Djongo translates 
Django ORM queries into MongoDB queries, providing some level of 
compatibility. 

2. Native MongoDB integration: Another approach is to bypass Django's ORM 
altogether and directly use the official MongoDB Python driver (PyMongo) to 
interact with MongoDB. This means you won't be using Django's ORM features 
and will need to handle database interactions manually. 

Ultimately, the choice depends on your specific project requirements and 
preferences. If you have a strong preference for using Django's ORM, you can 
explore the third-party package options. However, if your project heavily 
relies on MongoDB's features or if you need more flexibility, using the 
native MongoDB integration might be a better fit.


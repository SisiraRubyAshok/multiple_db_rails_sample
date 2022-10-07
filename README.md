Multiple db rails sample

primary and primary_replica database my_primary_database in mysql
animal and animal_replica database my_animals_database in postgresql

For replica database, you need to add a replica: true entry to the replica in the database.yml.
Replica database is replica of the other database which is used for reading the data

For new writer databases, you need to set the migrations_paths to the directory where you will store migrations for that database.

In order to use the my_animals_database we need to create a new abstract class (AnimalsRecord) and connect to the animals databases.

Classes that connect to primary/primary_replica can inherit from your primary abstract class like standard Rails applications Whereas Classes that connect to animal/animal_replica can inherit from AnimalsRecord.

The table dogs is created in my_animal_database
The table people is created in my_primary_database

Contain two schema animals_schema for animal database and schema for primary database

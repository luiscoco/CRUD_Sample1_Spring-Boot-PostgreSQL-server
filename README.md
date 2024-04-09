# CRUD Sample1 SpringBoot PostgreSQL server

## 1. How to install PostgreSQL

https://www.postgresql.org/download/

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/a022db1e-06d5-48af-be26-16bd84358a86)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/aadc0f26-0a5e-476b-a0b8-a9cecc71f72b)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/cc2e5f1b-9dab-430b-b63c-eb8ce4ac0519)

We run As Administrator the installer file and we proceed with the PostgreSQL installation

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/c0d12e0a-be80-475d-9f24-e3f2c27d7333)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/495d34d4-ad71-47bc-9e6c-fd30afd9845e)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/95713939-0cc9-4d25-9383-16f2f48050dd)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/ef6f992d-7aac-43f3-9b3d-942ad5f60511)

We set the password: Luiscoco123456#

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/d99d5dc1-a2cb-46e9-bc3a-1e53d6627634)

We select the PostgreSQL running port

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/a22a72b1-8a74-4d3a-bd6c-3d26595c0849)

We select the local configuration

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/df544b12-fddd-4972-b3d6-13fe85abbdc2)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/72a13562-8f63-4715-9112-0289ecc793f0)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/4b0bfc52-124c-4f34-8171-414784ad349d)

We run PgAdmin4 and we input and save the password

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/42333992-9a56-4b4c-9535-a15b763aa848)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/871f2893-d65f-4e9a-8257-b692cd55739e)

## 2. Create a new database(testdb) and a new table(tutorials)

We right click on the Databases and we create a new database called **testdb**

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/53bf2a08-aa16-4191-9fd3-ee366bff30b4)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/10087bce-de66-4039-8c7c-d46a198e5912)

We verify the database was created

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/b9758466-8291-496e-8130-947a2a897740)

Now we have to create the tutorials table. We right click on the Schema and Create a new Query

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/ac6545f1-2a76-454d-aa7d-88970a3df6c1)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/1ea2c633-0643-4322-815d-9bf89dd790d8)

We confirm we created a new table called **tutorials**

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/dc96c361-7b4d-4fdf-8e8e-45eee36e77ca)

## 3. Source code explanation

### 3.1. Dependencies and libraries

The dependencies included in this project are:

- spring-boot-starter-data-jpa

- spring-boot-starter-web

- postgresql

- spring-boot-starter-test

This sample is configured for **Java 21**, hence do not forget to set the **JAVA_HOME** and/or **PATH** environmental variable in your local desktop to run this application

![image](https://github.com/luiscoco/CRUD_Sample1_spring-boot-mysql-server/assets/32194879/14d45f0d-c62e-4718-98fa-91618f770abe)

![image](https://github.com/luiscoco/CRUD_Sample1_spring-boot-mysql-server/assets/32194879/80386f51-a518-4256-b9f4-e51affab94b1)

We also can run this command to see the Java version installed in your computer:

```
java --version
```

![image](https://github.com/luiscoco/CRUD_Sample1_spring-boot-mysql-server/assets/32194879/47e181c6-f669-4c4b-af07-d480d428cbae)

We also specify the Java version in the **pom.xml** file:

```xml
<properties>
	<java.version>21</java.version>
</properties>
```

This is the whole pom.xml file:

**pom.xml**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.1.0</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.bezkoder</groupId>
	<artifactId>spring-boot-jpa-postgresql</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>spring-boot-jpa-postgresql</name>
	<description>Spring Boot, PostgreSQL example with Maven, Spring JPA</description>

	<properties>
		<java.version>21</java.version>
	</properties>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<groupId>org.postgresql</groupId>
			<artifactId>postgresql</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
			<exclusions>
				<exclusion>
					<groupId>org.junit.vintage</groupId>
					<artifactId>junit-vintage-engine</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```

### 3.2. Database connection string and other properties 

Regarding the database properties and connections string we set these values in the **application.properties** file:

**application.properties**

```
spring.datasource.url= jdbc:postgresql://localhost:5432/testdb
spring.datasource.username= postgres
spring.datasource.password= Luiscoco123456#

spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation= true
spring.jpa.properties.hibernate.dialect= org.hibernate.dialect.PostgreSQLDialect

# Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto= update
```

**IMPORTANT NOTE**

Do not forget to set in the application.properties file the PostgreSQL password as defined during installation

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/dd841ae9-6e5e-446e-9876-88d11284ad87)

### 3.3. Project folders and files structure

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/c327ccf0-7ce0-4d94-92ff-042246876390)

### 3.4. Project main entry point

```java
package com.bezkoder.spring.jpa.postgresql;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringBootJpaPostgresqlApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringBootJpaPostgresqlApplication.class, args);
	}

}
```

### 3.5. Data Model

```java
package com.bezkoder.spring.jpa.postgresql.model;

import jakarta.persistence.*;

@Entity
@Table(name = "tutorials")
public class Tutorial {

  @Id
  @GeneratedValue(strategy = GenerationType.AUTO)
  private long id;

  @Column(name = "title")
  private String title;

  @Column(name = "description")
  private String description;

  @Column(name = "published")
  private boolean published;

  public Tutorial() {

  }

  public Tutorial(String title, String description, boolean published) {
    this.title = title;
    this.description = description;
    this.published = published;
  }

  public long getId() {
    return id;
  }

  public String getTitle() {
    return title;
  }

  public void setTitle(String title) {
    this.title = title;
  }

  public String getDescription() {
    return description;
  }

  public void setDescription(String description) {
    this.description = description;
  }

  public boolean isPublished() {
    return published;
  }

  public void setPublished(boolean isPublished) {
    this.published = isPublished;
  }

  @Override
  public String toString() {
    return "Tutorial [id=" + id + ", title=" + title + ", desc=" + description + ", published=" + published + "]";
  }

}
```

### 3.6. Jpa Repository

```java
package com.bezkoder.spring.jpa.postgresql.repository;

import java.util.List;

import org.springframework.data.jpa.repository.JpaRepository;

import com.bezkoder.spring.jpa.postgresql.model.Tutorial;

public interface TutorialRepository extends JpaRepository<Tutorial, Long> {
  List<Tutorial> findByPublished(boolean published);

  List<Tutorial> findByTitleContaining(String title);
}
```

### 3.7. Controller

```java
package com.bezkoder.spring.jpa.postgresql.controller;

import java.util.ArrayList;
import java.util.List;
import java.util.Optional;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.CrossOrigin;
import org.springframework.web.bind.annotation.DeleteMapping;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.PutMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

import com.bezkoder.spring.jpa.postgresql.model.Tutorial;
import com.bezkoder.spring.jpa.postgresql.repository.TutorialRepository;

@CrossOrigin(origins = "http://localhost:8081")
@RestController
@RequestMapping("/api")
public class TutorialController {

	@Autowired
	TutorialRepository tutorialRepository;

	@GetMapping("/tutorials")
	public ResponseEntity<List<Tutorial>> getAllTutorials(@RequestParam(required = false) String title) {
		try {
			List<Tutorial> tutorials = new ArrayList<Tutorial>();

			if (title == null)
				tutorialRepository.findAll().forEach(tutorials::add);
			else
				tutorialRepository.findByTitleContaining(title).forEach(tutorials::add);

			if (tutorials.isEmpty()) {
				return new ResponseEntity<>(HttpStatus.NO_CONTENT);
			}

			return new ResponseEntity<>(tutorials, HttpStatus.OK);
		} catch (Exception e) {
			return new ResponseEntity<>(null, HttpStatus.INTERNAL_SERVER_ERROR);
		}
	}

	@GetMapping("/tutorials/{id}")
	public ResponseEntity<Tutorial> getTutorialById(@PathVariable("id") long id) {
		Optional<Tutorial> tutorialData = tutorialRepository.findById(id);

		if (tutorialData.isPresent()) {
			return new ResponseEntity<>(tutorialData.get(), HttpStatus.OK);
		} else {
			return new ResponseEntity<>(HttpStatus.NOT_FOUND);
		}
	}

	@PostMapping("/tutorials")
	public ResponseEntity<Tutorial> createTutorial(@RequestBody Tutorial tutorial) {
		try {
			Tutorial _tutorial = tutorialRepository
					.save(new Tutorial(tutorial.getTitle(), tutorial.getDescription(), false));
			return new ResponseEntity<>(_tutorial, HttpStatus.CREATED);
		} catch (Exception e) {
			return new ResponseEntity<>(null, HttpStatus.INTERNAL_SERVER_ERROR);
		}
	}

	@PutMapping("/tutorials/{id}")
	public ResponseEntity<Tutorial> updateTutorial(@PathVariable("id") long id, @RequestBody Tutorial tutorial) {
		Optional<Tutorial> tutorialData = tutorialRepository.findById(id);

		if (tutorialData.isPresent()) {
			Tutorial _tutorial = tutorialData.get();
			_tutorial.setTitle(tutorial.getTitle());
			_tutorial.setDescription(tutorial.getDescription());
			_tutorial.setPublished(tutorial.isPublished());
			return new ResponseEntity<>(tutorialRepository.save(_tutorial), HttpStatus.OK);
		} else {
			return new ResponseEntity<>(HttpStatus.NOT_FOUND);
		}
	}

	@DeleteMapping("/tutorials/{id}")
	public ResponseEntity<HttpStatus> deleteTutorial(@PathVariable("id") long id) {
		try {
			tutorialRepository.deleteById(id);
			return new ResponseEntity<>(HttpStatus.NO_CONTENT);
		} catch (Exception e) {
			return new ResponseEntity<>(HttpStatus.INTERNAL_SERVER_ERROR);
		}
	}

	@DeleteMapping("/tutorials")
	public ResponseEntity<HttpStatus> deleteAllTutorials() {
		try {
			tutorialRepository.deleteAll();
			return new ResponseEntity<>(HttpStatus.NO_CONTENT);
		} catch (Exception e) {
			return new ResponseEntity<>(HttpStatus.INTERNAL_SERVER_ERROR);
		}

	}

	@GetMapping("/tutorials/published")
	public ResponseEntity<List<Tutorial>> findByPublished() {
		try {
			List<Tutorial> tutorials = tutorialRepository.findByPublished(true);

			if (tutorials.isEmpty()) {
				return new ResponseEntity<>(HttpStatus.NO_CONTENT);
			}
			return new ResponseEntity<>(tutorials, HttpStatus.OK);
		} catch (Exception e) {
			return new ResponseEntity<>(HttpStatus.INTERNAL_SERVER_ERROR);
		}
	}

}
```

## 4. How to run the Server SpringBoot application

### 4.1. We first run the Server SpringBoot application

Run MySQL Workbench and enter in the database testdb

```
mvn spring-boot:run
```

or

```
mvn spring-boot:run -X
```

We confirm the SpringBott server application is running in Tomcat in port 8080

### 4.2. We now run the Client Angular front-end application

The Client app source code is stored in this github repo: https://github.com/luiscoco/CRUD_Sample1_angular-17-client

We install the application dependencies with this command:

```
npm i
```

or

```
npm install
```

Then we run the angular application in port 8081

```
ng serve --port 8081
```

We verify the angular application running

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/7795e550-0ad7-49dc-bdfd-590ad60929ef)

We select the **Add** menu option and we add a **new item** to the list

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/fda25d27-a31f-4235-bd49-ce84e581d9a7)

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/dd560f58-82f0-4cf6-9068-21ea92c23e7d)

We select the Tutorials menu option and we **click on the new item created**

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/2cb5c6ea-7b72-4dc6-86b7-745370db09a2)

If we open **pg Admin 4** we can also see the new item in the database testdb and table tutorials

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/97b9eb33-c6dc-46f2-9886-2a2a554800d8)

We can also **edit** the created item pressing on the item and then in the Edit button

![image](https://github.com/luiscoco/CRUD_Sample1_Spring-Boot-PostgreSQL-server/assets/32194879/9c33b855-cf94-4eed-8793-f243f7e3b153)




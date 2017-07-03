# gs-routing-and-filtering-with-netflix-zuul

This is a repository for future reference about how to route and filter requests to a Spring Boot microservice application using the Netflix Zuul edge service library.

It was based in [Routing and Filtering](https://spring.io/guides/gs/routing-and-filtering/) tutorial.

### Instructions to run the 'book microservice' and 'gateway'
1. Clone this repository
2. So, go to the project root folder and type `cd book`
3. You must choose **one** of the four alternatives bellow to build and run the book microservice:
    1. Alternative 1: If you prefer to use Gradle, run the command `./gradlew bootRun` on root folder
    2. Alternative 2: Or you can build the JAR file using `./gradlew build` and then running the JAR file<br /> `java -jar build/libs/book-0.0.1-SNAPSHOT.jar`
    3. Alternative 3: If you prefer to use Maven, run the command `./mvnw spring-boot:run` also on root folder
    4. Alternative 4: Or you can yet build the JAR file using `./mvnw clean package` and then running the JAR file<br /> `java -jar target/book-0.0.1-SNAPSHOT.jar`
4. After this, the microservice is up. If you visit http://localhost:8090/available you will get a message like this: "*Spring in Action*".

5. So, open another terminal in the project root again and type `cd gateway`
6. You must choose **one** of the four alternatives bellow to build and run the gateway:
    1. Alternative 1: If you prefer to use Gradle, run the command `./gradlew bootRun` on root folder
    2. Alternative 2: Or you can build the JAR file using `./gradlew build` and then running the JAR file<br /> `java -jar build/libs/gateway-0.0.1-SNAPSHOT.jar`
    3. Alternative 3: If you prefer to use Maven, run the command `./mvnw spring-boot:run` also on root folder
    4. Alternative 4: Or you can yet build the JAR file using `./mvnw clean package` and then running the JAR file<br /> `java -jar target/gateway-0.0.1-SNAPSHOT.jar`
7. After this, the microservice is up. If you visit http://localhost:8080/books/available you will get a message like this: "*Spring in Action*". And note into the terminal some logged messages like this:
>2017-07-03 13:56:34.005  INFO 65929 --- [nio-8080-exec-2] hello.filters.pre.SimpleFilter           : GET request to http://localhost:8080/books/available

### About development environment

- Java 1.8.0_25
- Spring Boot 1.4.0
- Gradle 4.0
- Groovy 2.4.11
- Gradle Wrapper 2.9
- Ant 1.9.6
- Apanche Maven 3.5.0
- POM Model 4.0.0
- Takari Maven Wrapper 0.1.5
- Mac OS 10.12.5 x86_64
- Eclipse IDE Neon 4.6.3
- Atom 1.18.0 x64
- Git 2.8.1
- Tower 2.4.0 for OSx

## Some concepts

**Netflix Zuul** - Zuul is a gateway service that provides dynamic routing, monitoring, resiliency, security, and more.

**Reverse Proxy** -
> "In computer networks, a reverse proxy is a type of proxy server that retrieves resources on behalf of a client from one or more servers. These resources are then returned to the client like they originated from the Web server itself. Contrary to a forward proxy, which is an intermediary for its associated clients to contact any server, a reverse proxy is an intermediary for its associated servers to be contacted by any client."" ([Reverse Proxy @wikipedia](https://en.wikipedia.org/wiki/Reverse_proxy))


## Some other details

### Used annotation
- @RestController
- @RequestMapping(value = "/available")
- @RequestMapping(value = "/checked-out")
- @SpringBootApplication
- @EnableZuulProxy
- @Bean

#### Related annotation
- @Configuration
- @EnableAutoConfiguration
- @EnableWebMvc
- @ComponentScan

#### Annotations used on test case
- @RunWith(SpringRunner.class)
- @SpringBootTest(webEnvironment= SpringBootTest.WebEnvironment.RANDOM_PORT)
- @SpringBootTest(webEnvironment= SpringBootTest.WebEnvironment.RANDOM_PORT, classes = GatewayApplication.class)
- @Autowired
- @BeforeClass
- @AfterClass
- @Before
- @Test
- @Rule

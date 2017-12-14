# Hermes
Java based Web-Crawler

Note: This project will keep getting enhanced till qualification/requirements are pushed forth. Due to lack of time, it's quite basic.

[crawler4j](https://github.com/yasserg/crawler4j/) is a widely used web crawler for Java however uses basic threading and monitor threads to achieve its concurrency. I reckon its implementation can be simplified using [java.util.concurrent](https://docs.oracle.com/javase/8/docs/api/index.html?java/util/concurrent/package-summary.html)'s battle-hardened classes for automating the thread execution and handling.

## Requirements/Built With
* [Java](http://https://java.com/download/) - (Oracle Java (JDK jdk1.8.0_151 64-bit))
* [Spring Boot](http://spring.io) - Yeah
* [Maven](https://maven.apache.org/) - Dependency Management

## Building and running:
Generate a .jar by executing the following command in the project folder:

```mvn clean package```

Run it using:

```mvn spring-boot:run```

### Enhancements
* Respect /robots.txt (Good people respect other people)
* Multi-threaded model using java.util.concurrent ExecutorService while using LinkedBlockingQueue or FixedThreadPool to limit the maximum concurrency

## Usage
There are two interfaces exposed for the crawler. HTTP and REST
The HTTP endpoint may be accessed by:

```http://127.0.0.1:8080/crawler```

REST requests (POST) may be dispatched to:

```http://127.0.0.1:8080/crawl```

with UrlCrawl object being serialized as JSON and provided in the request.
Example POST request payload:
```
{
	"url": "http://www.google.com",
	"depth" : "3",
	"traversalLimit" : "100"
}
```

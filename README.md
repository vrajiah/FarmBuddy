# Farm Buddy
[![Build Status](https://travis-ci.com/vrajiah/farm-buddy.svg?branch=master)](https://travis-ci.com/github/vrajiah/farm-buddy?branch=master)
[![Coverage Status](https://coveralls.io/repos/github/vrajiah/farm-buddy/badge.svg?branch=master)](https://coveralls.io/github/vrajiah/farm-buddy?branch=master)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=vrajiah_farm-buddy&metric=alert_status)](https://sonarcloud.io/dashboard?id=vrajiah_farm-buddy)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/d3f2ff62c1474bcabad601b9e4ea2c12)](https://www.codacy.com/manual/vrajiah/farm-buddy?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=vrajiah/farm-buddy&amp;utm_campaign=Badge_Grade)

## About Farm Buddy
This project contains a simple solution that allows Farmers to use water efficiently on their farms.

When a harsh drought hit any region, access to water is limited. And, farmers tend to over (or) under utilize available water resulting in lesser yeilds.

FarmBuddy assist farmers to maximize yeild by closely monitoring soil moisture and air temperature to regulate the water usage.
```text
1. Monitoring soil moisture content using sensor and arduino kit
2. and report sensor data back to cloud
3. Retrieve weather data for the location over a period of years (like average precipitation etc.,)
4. Based on the soil nature, moisture on the soil and with historic weather data for the month suggest farmers how much to water to be used over SMS.
5. And, this will lead to optimal use of water and more yeilds.
```
## Requirements
For building and running the application you need:
-   [JDK 1.8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
-   [Maven 3](https://maven.apache.org)

## Running the application using the command-line

This project can be built with [Apache Maven](http://maven.apache.org/). 

Use the following steps to run the application locally:
-   Execute full Maven build to create the `target/farm-buddy-0.0.1-SNAPSHOT.jar` file:
    ```bash
    mvn clean install
    ```

-   Execute and start application using,
    ```bash
    mvn spring-boot:run
    ```
  
> Once the server is running, the application will be available under [http://localhost:8080/](http://localhost:8080/)
  
## Water Usage Prediction
Request
```$xslt
 http://localhost:8080/predict?crop=Paddy&mobile=<mobile#>
```

Response
```$xslt
{
  "data": {
    "type": "report",
    "id": "686160b0-5e35-4e94-ad91-47c7a887509d",
    "attributes": {
      "mobile": "<mobile#>",
      "crop": "Paddy",
      "soilMoisture": 67,
      "avgPrecipitation": 94,
      "avgEvapotranspiration": 5,
      "message": "Water required for your Paddy field is 94 litres per day for an Acre"
    }
  }
}
```

> Note: [How to use soil moisture sensor with arduino](https://create.arduino.cc/projecthub/MisterBotBreak/how-to-use-a-soil-moisture-sensor-ce769b)

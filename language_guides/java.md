# Java Guide for OpenAI API Key

This guide provides instructions on how to use the OpenAI API Key with Java. It covers the setup process, making API calls, handling responses, and error handling.

## Table of Contents

1. [Setup](#setup)
2. [Making API Calls](#making-api-calls)
3. [Handling Responses](#handling-responses)
4. [Error Handling](#error-handling)

## Setup

To use the OpenAI API with Java, you need to add the OpenAI Java client library to your project. If you're using Maven, you can add the following dependency to your `pom.xml` file:

```xml
<dependency>
  <groupId>com.openai</groupId>
  <artifactId>openai</artifactId>
  <version>0.0.1</version>
</dependency>
```

Then, import the library in your Java class:

```java
import com.openai.*;
```

Set your API key:

```java
OpenAI.setApiKey("your-api-key");
```

## Making API Calls

Here's an example of how to make an API call:

```java
Completion completion = OpenAI.Completion.create(
  "text-davinci-002",
  "Translate the following English text to French: '{}'",
  60
);
```

## Handling Responses

The response from the API call is a `Completion` object. You can access the generated text with the `getText()` method:

```java
String text = completion.getText();
```

## Error Handling

If there's an error with the API call, the library will throw an `OpenAIException`. You should catch this exception and handle it appropriately:

```java
try {
  Completion completion = OpenAI.Completion.create(
    "text-davinci-002",
    "Translate the following English text to French: '{}'",
    60
  );
} catch (OpenAIException e) {
  e.printStackTrace();
}
```

Please refer to the OpenAI API documentation for more detailed information on how to use the API with Java.

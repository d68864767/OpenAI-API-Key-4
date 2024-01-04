# Text Response Type

The OpenAI API can return responses in Text format. Text format is the simplest form of data interchange format that is easy for humans to read and write and easy for machines to parse and generate.

## Overview

Text is a format that is completely language independent and can be used in any programming language. These properties make Text an ideal data-interchange language.

## Working with Text in OpenAI API

When you make a request to the OpenAI API, you can specify the response format as Text. Here is an example of how to do this:

```python
import openai

openai.api_key = 'your-api-key'

response = openai.Completion.create(
  engine="davinci-codex",
  prompt="Translate the following English text to French: '{}'",
  max_tokens=60,
  format="text"
)

print(response.choices[0].text.strip())
```

In this example, the `format` parameter is set to "text". The response from the API will be a plain text string.

## Parsing Text Response

Once you receive a Text response, you can directly use it in your application. Here is an example of how to use a Text response:

```python
# Assume `response` is the Text response received from the OpenAI API

# Accessing data in the response
text = response.choices[0].text.strip()
print(text)
```

In this example, the response is a plain text string and you can directly use it in your application.

## Conclusion

Text is a simple and widely used data format. The ability to receive responses from the OpenAI API in Text format allows for easy integration with many different programming languages and systems.

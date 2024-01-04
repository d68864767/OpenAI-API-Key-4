# Custom Formats Response Type

The OpenAI API can return responses in custom formats. Custom formats are user-defined formats that can be used when the standard formats (JSON, Text, HTML) do not meet the specific needs of your application.

## Overview

Custom formats are flexible and can be designed to fit the specific requirements of your application. They can be used to structure the response data in a way that is most convenient for your application to process.

## Working with Custom Formats in OpenAI API

When you make a request to the OpenAI API, you can specify the response format as a custom format. Here is an example of how to do this:

```python
import openai

openai.api_key = 'your-api-key'

response = openai.Completion.create(
  engine="davinci-codex",
  prompt="Translate the following English text to French: '{}'",
  max_tokens=60,
  format="custom"
)

print(response.choices[0].text.strip())
```

In this example, the `format` parameter is set to "custom". The response from the API will be a string formatted according to the custom format you have defined.

## Parsing Custom Format Response

Once you receive a response in a custom format, you will need to parse it according to the rules you have defined for your custom format. Here is an example of how to parse a response in a custom format:

```python
# Assume `response` is the response received from the OpenAI API in a custom format

# Parsing the response according to the rules of the custom format
parsed_response = custom_format_parser(response)

# Accessing data in the parsed response
text = parsed_response.get_text().strip()
print(text)
```

In this example, `custom_format_parser` is a function that you have defined to parse responses in your custom format. The parsed response is an object of a type that you have defined, and you can access its elements using the methods you have defined for that type.

## Conclusion

Custom formats provide a high degree of flexibility and can be used to tailor the API responses to the specific needs of your application. The ability to receive responses from the OpenAI API in custom formats allows for easy integration with many different programming languages and systems.

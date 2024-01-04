# Ruby Guide for OpenAI API Key

This guide provides instructions on how to use the OpenAI API Key with Ruby. It covers the setup process, making API calls, handling responses, and error handling.

## Table of Contents

1. [Setup](#setup)
2. [Making API Calls](#making-api-calls)
3. [Handling Responses](#handling-responses)
4. [Error Handling](#error-handling)

## Setup

To use the OpenAI API with Ruby, you need to install the OpenAI Ruby client library. You can install it using gem:

```bash
gem install openai
```

Then, require the library in your Ruby script:

```ruby
require 'openai'
```

Set your API key:

```ruby
Openai.api_key = 'your-api-key'
```

## Making API Calls

Here's an example of how to make an API call:

```ruby
response = Openai::Completion.create(
  engine: "text-davinci-002",
  prompt: "Translate the following English text to French: '{}'",
  max_tokens: 60
)
```

## Handling Responses

The API response is a JSON object. Here's how to extract information from the response:

```ruby
translated_text = response['choices'][0]['text']
puts translated_text
```

## Error Handling

If the API call fails, an exception will be raised. Here's how to handle exceptions:

```ruby
begin
    response = Openai::Completion.create(
      engine: "text-davinci-002",
      prompt: "Translate the following English text to French: '{}'",
      max_tokens: 60
    )
rescue Openai::Error => e
    puts e.message
end
```

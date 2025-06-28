# Black Box Challenge API Endpoint Analysis Report

## Introduction
This report details the reverse-engineering process and findings for the Black Box Challenge API endpoints. The objective was to understand the behavior of each undocumented API endpoint through systematic experimentation and document the observed patterns.

## Methodology
The approach involved interacting with each endpoint using various inputs and observing the corresponding outputs. A Python script was developed to automate these interactions and capture the responses. The browser-based interface at `https://blackbox-interface.vercel.app/` was also utilized for initial manual testing and observation of network requests.

## Endpoint Analysis




### POST /data
- **Input:** Accepts a string.
- **Observed Behavior:** The endpoint returns the Base64 encoded version of the input string. For example, inputting `test` resulted in `dGVzdA==`.
- **Conclusion:** This endpoint performs Base64 encoding on the provided string input.




### GET /time
- **Input:** No input required.
- **Observed Behavior:** The endpoint returns the current server time in a JSON format, e.g., `{"time": "2025-06-28T08:32:40.000Z"}`.
- **Conclusion:** This endpoint provides the current server time.




### POST /fizzbuzz
- **Input:** Accepts an integer.
- **Observed Behavior:** This endpoint implements the classic FizzBuzz game logic. 
  - If the input number is divisible by both 3 and 5, it returns `FizzBuzz`.
  - If divisible by 3, it returns `Fizz`.
  - If divisible by 5, it returns `Buzz`.
  - Otherwise, it returns the number itself.
  - If a non-numeric input is provided, it returns `false`.
- **Conclusion:** This endpoint is a FizzBuzz calculator.




### POST /zap
- **Input:** Accepts a string.
- **Observed Behavior:** The endpoint returns the input string as is. For example, inputting `test` resulted in `test`.
- **Conclusion:** This endpoint appears to be an echo service, returning the input directly.




### POST /alpha
- **Input:** Accepts a string.
- **Observed Behavior:** The endpoint returns `true` if the input string contains only alphabetic characters, and `false` otherwise. For example, `abc` returns `true`, while `123` returns `false`.
- **Conclusion:** This endpoint validates if the input string is purely alphabetic.




### POST /glitch
- **Input:** Accepts a string.
- **Observed Behavior:** The endpoint returns the reverse of the input string. For example, inputting `hello` resulted in `olleh`.
- **Conclusion:** This endpoint reverses the provided string input.



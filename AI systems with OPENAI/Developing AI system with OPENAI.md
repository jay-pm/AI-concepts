<span style="background:green">## AI Systems with OpenAI</span>
<span style="color:blue">Blue text</span>
<span style="color:blue">**Common Error Types:**</span>
1. InternalServerError, APIConnectionError, APITimeoutError: These errors are usually due to server or connection issues. Solutions include checking your connection, waiting, and retrying, or contacting support.
2. RateLimitError, ConflictError: These occur when request limits are exceeded. You can solve this by reducing request size or frequency.
3. AuthenticationError: This happens when the API key is invalid or expired. Ensure your API key is correct and active.
4. BadRequestError: This indicates malformed requests or missing parameters. Review the error message and documentation to correct the input.

**TRY & EXCEPT**:
To manage exceptions, use try and except blocks. This allows your program to continue running even when an error occurs.


```python
# Set up your OpenAI API key
client = OpenAI(api_key="<OPENAI_API_TOKEN>")

# Use the try statement
try: 
    response = client.chat.completions.create(
        model="gpt-3.5-turbo",
        messages=[message]
    )
    # Print the response
    print(response.choices[0].message.content)
# Use the except statement
except openai.AuthenticationError as e:
    print("Please double check your authentication key and try again, the one provided is not valid.")
```
We have to handling rate limits when using the OpenAI API, which ensures smooth data flow and prevents excessive requests. Here are the key points:
- Rate Limits: These are restrictions on the number of requests or tokens you can send to the API in a given timeframe. They help prevent overloading the system and ensure fair usage.
- Retry Decorators: Use Python's Tenacity library to automatically retry requests when rate limits are hit. This involves:
    - **wait_random_exponential()**: Configures exponential backoff for retries.
    - **stop_after_attempt()**: Limits the number of retry attempts.

```python
from tenacity import retry, stop_after_attempt, wait_random_exponential

@retry(wait=wait_random_exponential(min=5, max=40), stop=stop_after_attempt(4))
def get_response(model, message):
    response = client.chat.completions.create(model=model, messages=[message])
    return response.choices[0].message.content
```
- Batching Requests: Instead of sending multiple requests in a loop, we can send them in batches. This reduces the frequency of requests and helps avoid rate limits.
- Token Limits: We can measure and reduce tokens in a request using the tiktoken library to ensure they stay within the allowed limits.
These techniques help build more robust and efficient AI systems by managing API usage effectively.

### Function calling
- Function calling enables the use of custom functions as input to the OpenAI endpoint, resulting in improved consistency of the responses.
- Can be used to enhance the responses by integrating with external APIs, such as for a weather chatbot calling an API to return current temperatures at specific locations
- Allows our AI system to interact programmatically with other functions and applications


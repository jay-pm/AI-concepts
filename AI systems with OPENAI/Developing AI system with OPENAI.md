<span style="background:green"> ## AI Systems with OpenAI</span>
<span style="color:blue">Blue Text</span>  
<span style="color:blue">**Common Error Types:**</span>
1. InternalServerError, APIConnectionError, APITimeoutError: These errors are usually due to server or connection issues. Solutions include checking your connection, waiting, and retrying, or contacting support.
2. RateLimitError, ConflictError: These occur when request limits are exceeded. You can solve this by reducing request size or frequency.
3. AuthenticationError: This happens when the API key is invalid or expired. Ensure your API key is correct and active.
4. BadRequestError: This indicates malformed requests or missing parameters. Review the error message and documentation to correct the input.

**TRY & EXCEPT**:
To manage exceptions, use try and except blocks. This allows your program to continue running even when an error occurs.

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

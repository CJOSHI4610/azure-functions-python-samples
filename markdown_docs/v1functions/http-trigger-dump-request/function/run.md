## FunctionDef write_http_response(status, body_dict)
**write_http_response**: The function of write_http_response is to construct an HTTP response with a specified status, body, and headers.

**parameters**:
- status: The HTTP status code to be included in the response.
- body_dict: A dictionary containing the body content of the response.

**Code Description**:
The write_http_response function takes in a status code and a dictionary representing the body content. It constructs a response dictionary with the provided status, body (converted to JSON format), and a fixed "Content-Type" header set to "application/json". The function then opens a file for writing the response using the environment variable _AZURE_FUNCTION_HTTP_OUTPUT_ENV_NAME and writes the JSON-serialized response dictionary to the file.

**Note**:
- Ensure that the environment variable _AZURE_FUNCTION_HTTP_OUTPUT_ENV_NAME is properly set before calling this function to avoid errors.
- Make sure that the body_dict parameter is a valid dictionary that can be serialized to JSON.

**Output Example**:
{
    "status": 200,
    "body": "{\"key\": \"value\"}",
    "headers": {
        "Content-Type": "application/json"
    }
}

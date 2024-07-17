## FunctionDef write_http_response(status, body_dict)
**write_http_response**: The function of write_http_response is to generate an HTTP response with a specified status, body, and headers in JSON format.

**parameters**:
- status: An integer representing the HTTP status code.
- body_dict: A dictionary containing the body of the HTTP response.

**Code Description**: 
The write_http_response function takes in a status code and a dictionary of the response body. It constructs a response dictionary with the provided status, body (converted to JSON format), and a fixed header specifying the content type as "application/json". The function then returns the response dictionary as a JSON string.

In the project, the write_http_response function is utilized within the main function of the HTTP trigger. It is used to generate various HTTP responses based on different conditions such as configuration errors, invalid requests, and successful token generation. The main function calls write_http_response to return appropriate responses to the HTTP client.

**Note**: 
- Ensure that the status code provided is valid and corresponds to the HTTP status codes.
- The body_dict parameter should be a dictionary that can be converted to JSON format.

**Output Example**: 
```json
{
    "status": 200,
    "body": "{\"token\": \"example_token\", \"url\": \"example_url\"}",
    "headers": {
        "Content-Type": "application/json"
    }
}
```
## FunctionDef generate_sas_token(storage_account, storage_key, permission, token_ttl, container_name, blob_name)
**generate_sas_token**: The function of generate_sas_token is to create a Shared Access Signature (SAS) token for Azure Blob Storage resources.

**parameters**:
- storage_account: The name of the Azure Storage account.
- storage_key: The access key for the Azure Storage account.
- permission: The permission level for the SAS token.
- token_ttl: The time-to-live for the SAS token.
- container_name: The name of the container in Azure Blob Storage.
- blob_name (optional): The name of the blob in Azure Blob Storage.

**Code Description**:
The `generate_sas_token` function generates a SAS token for accessing Azure Blob Storage resources. It constructs input values based on the provided parameters, creates a base64 encoded signature using HMAC-SHA256, and then generates a query string for the SAS token. Depending on the presence of the `blob_name` parameter, it constructs the SAS URL accordingly. The function returns a dictionary containing the SAS token and the corresponding URL.

This function is called within the `main` function in the same file to generate a SAS token for Azure Blob Storage resources based on the input parameters received through an HTTP request. The SAS token is then used to provide temporary access to the specified Azure Blob Storage resources.

**Note**:
Ensure that the necessary parameters are provided correctly to generate a valid SAS token.
Make sure to handle the SAS token securely as it provides temporary access to Azure Blob Storage resources.

**Output Example**:
{
    'token': 'sv=XXXX&ss=b&srt=o&sp=r&se=XXXX&st=XXXX&spr=https&sig=XXXX',
    'url': 'https://storage_account.blob.core.windows.net/container_name/blob_name?sv=XXXX&ss=b&srt=o&sp=r&se=XXXX&st=XXXX&spr=https&sig=XXXX'
}
## FunctionDef main(req)
Doc is waiting to be generated...

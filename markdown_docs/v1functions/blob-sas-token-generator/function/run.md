## FunctionDef write_http_response(status, body_dict)
**write_http_response**: The function of write_http_response is to generate an HTTP response with a specified status code, body content, and headers.

**parameters**:
- status: Represents the HTTP status code to be included in the response.
- body_dict: A dictionary containing the body content of the response.

**Code Description**:
The write_http_response function takes in a status code and a dictionary of body content. It then constructs a response dictionary with the provided status code, body content (converted to JSON format), and sets the "Content-Type" header to "application/json". The function then opens the output stream using the Azure Function environment variable _AZURE_FUNCTION_HTTP_OUTPUT_ENV_NAME and writes the JSON-serialized response dictionary to the output stream.

**Note**:
- Ensure that the _AZURE_FUNCTION_HTTP_OUTPUT_ENV_NAME environment variable is properly set before calling this function to avoid errors.
- The body_dict parameter should be a dictionary that can be serialized to JSON format.

**Output Example**:
{
    "status": 200,
    "body": "{\"key\": \"value\"}",
    "headers": {
        "Content-Type": "application/json"
    }
}
## FunctionDef generate_sas_token(storage_account, storage_key, permission, token_ttl, container_name, blob_name)
**generate_sas_token**: The function of generate_sas_token is to generate a Shared Access Signature (SAS) token for Azure Blob Storage.

**parameters**:
- storage_account: The name of the Azure Storage account.
- storage_key: The key of the Azure Storage account.
- permission: The permissions to be assigned to the SAS token.
- token_ttl: The time-to-live for the SAS token.
- container_name: The name of the container in the Azure Storage account.
- blob_name (optional): The name of the blob in the container.

**Code Description**:
The function first sets the start time and expiry time for the SAS token, constructs an input value based on the provided parameters, creates a base64 encoded signature using HMAC-SHA256, generates a query string with the required parameters, and then constructs the SAS token URL based on whether a blob name is provided or not. Finally, it returns a dictionary containing the SAS token and the URL.

**Note**:
- Ensure that the necessary permissions are correctly set to avoid unauthorized access.
- Make sure to handle the SAS token securely as it provides access to the Azure Storage resources.

**Output Example**:
{
    'token': 'sv=_AZURE_STORAGE_API_VERSION&ss=b&srt=o&sp=permission&se=expiry_time&st=start_time&spr=https&sig=base64_encoded_signature',
    'url': 'https://storage_account.blob.core.windows.net/container_name/blob_name?query_string'
}

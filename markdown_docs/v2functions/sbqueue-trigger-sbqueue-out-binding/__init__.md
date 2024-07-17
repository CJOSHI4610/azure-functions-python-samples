## FunctionDef main(msgIn, msgOut)
**main**: The function of main is to process a Service Bus Queue message by decoding the message body and setting the output message with the same body content.
**parameters**:
- msgIn: func.ServiceBusMessage (input parameter representing the incoming Service Bus message)
- msgOut: func.Out[str] (output parameter for setting the outgoing message)

**Code Description**:
The main function starts by decoding the body of the incoming Service Bus message using the 'utf-8' encoding. It then logs a message indicating that the Service Bus Queue message has been processed, including the content of the message body. Finally, the function sets the content of the outgoing message to be the same as the decoded body of the incoming message.

**Note**:
Developers using this function should ensure that the input message (msgIn) is a valid Service Bus message and that the output message (msgOut) is set accordingly with the desired content. Additionally, any specific logging configurations or message processing requirements should be considered within the function.

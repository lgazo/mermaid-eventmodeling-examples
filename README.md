GitHub currently runs the following Mermaid version:

```mermaid
  info
```

Example of event model in a markdown document rendered in GitHub

```mermaid
eventmodeling

tf 01 ui CartUI
tf 02 cmd AddItem [[AddItem01]]
tf 03 evt ItemAdded [[ItemAdded]]
tf 04 cmd AddItem [[AddItem02]]
tf 05 evt ItemAdded [[ItemAdded]]

data AddItem01 {
  description: 'john'
  image: 'avatar_john'
  price: 20.4
}

data AddItem02 {
  description: 'jack'
  image: 'avatar_jack'
  price: 12.5
}

data ItemAdded {
  description: string
  image: string
  price: number
}
```


```mermaid

eventmodeling

tf 01 rmo Pending_Questions { How many invoices were sent out yesterday? }
tf 02 pcr Agent_A
tf 03 cmd InvokeModel { question }
tf 04 evt InvocationCompleted
tf 05 rmo InvocationResult { callTool: findInvoices }
rf 06 rmo Invoices
tf 07 pcr Agent_A ->> 05 ->> 06
tf 08 cmd InvokeModel { toolResult }
tf 09 evt InvocationCompleted
tf 10 rmo Answers [[Answers10]]
rf 11 rmo InvocationResult
tf 12 pcr AgentB

data Answers10 {
  2 invoices were sent out 
  yesterday to customers X and Y
}
```


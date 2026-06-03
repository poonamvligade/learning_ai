To build collaborative agents, Google invented the A2A protocol, and donated to linux foundation now.

### Agents need to talk!

<img width="813" height="379" alt="Screenshot 2026-05-26 at 9 50 34 AM" src="https://github.com/user-attachments/assets/e8689eb5-d12d-44e8-a709-ae1f9aa60f7a" />

what if you want mulitple agnets to work together on complex probelms. think of planning a trip you will need a flight agent , hotel agent,
activity agent, trvael agent and so on to co-ordinate with each other.

it shared to build all inside one company so people started using each other;s agent but they should follow standard methods
and expose same info so thta anybody can call them for their purpose

every a2a agent trnasmits standardised info about itself and supports same public methods, so it can be called by any other agant to complete tasks
which opens up all sorts of new orchestartion scenarios.

### A2A protocol
open protocol to handle agent-to-agent communication
<img width="903" height="276" alt="Screenshot 2026-05-26 at 9 45 14 AM" src="https://github.com/user-attachments/assets/52d95510-734b-49ac-97f9-6e05da7c5d9a" />
A2a facilitates communication between end user, a client agent and a remote/server agent.

A client agent is responsible for creating requests and hadling end user interaction.
while the remote user is responsible for acting on these reqauest in an attempt to provide the correct info or take the accurate action.

Note: any given agent can act as a client or a remote agent, depending on the context.

Now, a standard is only as useful as its adoption. A2A is widely popular in S/w Development industry

### A2A Capbilities
<img width="911" height="307" alt="Screenshot 2026-05-26 at 9 49 25 AM" src="https://github.com/user-attachments/assets/82702e28-d39c-48a4-b370-34aa45bf4a53" />

A2A agents can dynamically discover and collaborate via standardized tasks, share multimodal content, handle long-running processes, and do all of this with enterprise-grade security. 
Every agent is opaque, which means the implementation details never need to be exposed to follow the protocol.
A2a is primarily focused on bridging the agents.

### How does the protocol work?
<img width="873" height="379" alt="Screenshot 2026-05-26 at 12 40 42 PM" src="https://github.com/user-attachments/assets/fae9e568-9fe3-4383-826f-c90da3b921bb" />

We will walk through a simple system where Agent A needs Agent B to do something, we will go through the core building blocks of A2A, and how they enable agent collaboration.

In the above diagram, agent A is the client agent, and agent B is the remote agent.

First of all, how does agent A even find agent B, and know what it can do?

<img width="873" height="387" alt="Screenshot 2026-05-26 at 12 42 29 PM" src="https://github.com/user-attachments/assets/34594b59-4a4c-4b6d-937d-321088aa41f3" />



Agent B publishes an agent card, think of it as a digital business card. It's a std json file, which is served at a well-known URI in an agent's domain. This card tells the agent everything  it needs to know to start a conversation.

Agent B's name
What it does, its HTTP endpoint URL for A2A communication, special skills it offers, special capabilities like streaming, and how to authenticate? You can think of this architecture like robots.txt for web crawlers, or a service registry, or a microservices architecture 
<img width="958" height="428" alt="Screenshot 2026-05-26 at 12 43 48 PM" src="https://github.com/user-attachments/assets/9f9ee2d9-7855-4fed-acd9-b9bd138b7b48" />

Once Agent A found Agent B, how do they actually talk?

<img width="907" height="422" alt="Screenshot 2026-05-26 at 2 38 14 PM" src="https://github.com/user-attachments/assets/6399466d-a3a8-4681-89a6-5a0987a4855c" />

A2A uses std https for secure communication. The envelope for their messages is JSON RPS 2.0, a simple-to-call function on a remote server.



<img width="870" height="429" alt="Screenshot 2026-05-26 at 3 06 25 PM" src="https://github.com/user-attachments/assets/65ebace4-1aaf-4a72-908d-b633870e8fa5" />

Inside these json rpc messages, we have key a2a object, a message 
### A message
It represents one turn in the conversation, like agent A asking a question.
3. It has a role, user, or agent, and contains parts.
4. A part is the actual content- could be plain text, a file, multimodal, or structured JSON data.

5. When agent B gets a request, if the request is simple and can be completed quickly, it might respond directly with a message containing an answer.
6. But how does Agent B actually process the request when Agent A calls it? That is the job of the agent executor
 
 ### agent Executor

<img width="896" height="442" alt="Screenshot 2026-05-31 at 5 37 34 PM" src="https://github.com/user-attachments/assets/6f36eb67-d20a-48d5-89c7-857290898a40" />

It's a class that you write, and it links the generic A2A protocol plumbing handled by the A2A SDK and the specific logic of our agent

<img width="896" height="442" alt="Screenshot 2026-05-31 at 5 54 18 PM" src="https://github.com/user-attachments/assets/37f99149-5177-4f91-8b83-9900766f324f" />
this is what makes agent intoa logo thta can be connected to other agents. The sdk worries baout http, json-rps and event managemnet.

with the executor we focus on what happens whne the gant processes its response?
what if agent b's tasks takes along time?
we cant just ake agent a wait on one request.

<img width="873" height="436" alt="Screenshot 2026-05-31 at 5 54 52 PM" src="https://github.com/user-attachments/assets/af9761c9-abc4-4438-9141-e857d16978b0" />
this is whaere the task object comes in.
<img width="877" height="431" alt="Screenshot 2026-06-02 at 11 40 30 PM" src="https://github.com/user-attachments/assets/2176665e-53d7-4330-9999-894eda2a4ca9" />
the task is teh job that agent needs to do. this task has an ID and  status with a lifecycle - submitted, working, maybe input required, if agent be nedds more info, finally completed or failed.

So an agent a sends an initial request., agnet B might quickly respond saying got it. I ahve create task 1,2  ,3 and its not working. agent a then knoiws this task id. to get the final summary, agent A can periodically call another a2a method, tasks get, asking whats the stautus of the tasks 1,2,3.

Agent B will respond with the latest task status, and eventually, that method will return the task completed. and the summary will be in the task. artifacts.

<img width="877" height="446" alt="Screenshot 2026-06-02 at 11 47 05 PM" src="https://github.com/user-attachments/assets/2f1a9a8e-88ae-429b-b517-3284b9bdf61e" />

### Task lifecycle and polling challenge

<img width="909" height="437" alt="Screenshot 2026-06-03 at 7 33 54 PM" src="https://github.com/user-attachments/assets/00f32b1c-8123-4e72-ad4d-903f6920c924" />

Now, polling can work for quick updates.

Step 4: streaming

<img width="916" height="434" alt="Screenshot 2026-06-03 at 7 34 54 PM" src="https://github.com/user-attachments/assets/1db05174-db91-4dc6-8595-04d2f4171208" />


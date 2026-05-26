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
open protocol to handle agnet to agent communication
<img width="903" height="276" alt="Screenshot 2026-05-26 at 9 45 14 AM" src="https://github.com/user-attachments/assets/52d95510-734b-49ac-97f9-6e05da7c5d9a" />
A2a facilitates communication between end user , a client agent and a remote/server agent.

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

A2A uses std https for secure communication. the envelop for thir messages is JSON Rpc 2.0

<img width="874" height="427" alt="Screenshot 2026-05-26 at 2 38 31 PM" src="https://github.com/user-attachments/assets/10d5c7c7-98ab-4587-b45c-7edcbdf2c4eb" />

<img width="870" height="429" alt="Screenshot 2026-05-26 at 3 06 25 PM" src="https://github.com/user-attachments/assets/65ebace4-1aaf-4a72-908d-b633870e8fa5" />


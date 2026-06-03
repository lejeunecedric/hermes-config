**I'm configuring my Hermes agent crew and sharing the info here !**  
   
**What is Hermes Agent ?**  
https://hermes-agent.nousresearch.com/  
   
**First thing first, the handbook here :**  
https://hermesatlas.com/guide/  
   
Then if need to go deeper, the official doc :   
https://hermes-agent.nousresearch.com/  
   
So we start with a basic install :   
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash  
   
I want different profiles with different gateways.  
We don't need Docker for that anymore, but Docker can be useful if you want complete separation of your agents  
https://hermes-agent.nousresearch.com/docs/user-guide/docker  
   
So with a basic install, we start with multiple agents running in the same instance.  
Doc is here : https://hermes-agent.nousresearch.com/docs/user-guide/multi-profile-gateways  
   
The gateway is the where you interact with the agent with external services (Whatsapp, Telegram...) so you want one per agent. The "agent" will be a profile, each can have a separate token provider, separate SOUL.md and config files, separate Telegram bot, etc.  
Choosing the right organisation, roles and naming for agents is an interesting exercise. Agents are not human, but you will interact with them with human language, that can be a trap.  

Hermes can delegate tasks to agents, so I prefer to have agents to be seen as “job description”  

- 1 agent per client project  
- Coders, documentalists, researchers, specialists  
- 1 office manager that runs the circus  
- 1 personal assistant
- 
Also Hermes offers project management through its Kanban features, more on that later  
   
**To Create profiles (once) :**  
hermes profile create coder  
hermes profile create personal-bot  
hermes profile create research  
   
**To configure each**  
coder setup  
personal-bot setup  
research setup  
   
**To install each gateway as a managed service :**  
coder gateway install  
personal-bot gateway install  
research gateway install  
   
To start them all  
coder gateway start  
personal-bot gateway start  
research gateway start  
   
The setup is pretty straight forward, but there may be some hiccups : the Signal connection needs an external service, signal-cli  that proved a little difficult : I managed by installing manually from https://github.com/AsamK/signal-cli, redo a PROFILENAME gateway setup and chat with PROFILENAME to finalize the setup

   
Next steps : memory configuration, Kanban...  
   

I'm configuring my Hermes agent crew and sharing the info here !

What is Hermes Agent ?
https://hermes-agent.nousresearch.com/

First thing first, the handbook here : 
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

To Create profiles (once) :
hermes profile create coder
hermes profile create personal-bot
hermes profile create research

To configure each :
coder setup
personal-bot setup
research setup

To install each gateway as a managed service :
coder gateway install
personal-bot gateway install
research gateway install

To start them all
coder gateway start
personal-bot gateway start
research gateway start


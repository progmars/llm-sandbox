I evaluated a few models that could run on my somewhat outdated PC with i7-7700 and 16GB RAM (a kit with 32GB will arrive next week) and a 4060 Ti 16GB.

My favorite kind of roleplay is to start with a scripted back-and-forth between characters and then to continue into free-ride mode.

When I just started playing with LLM roleplay, I was annoyed by how difficult it was to make the AI strictly follow a few general rules and the sequence of events in the scenario, unless I wrote the entire dialogue and followed it myself too. I almost gave up, but then one LLM pleasantly surprised me and made me believe that it is possible. But that model has another annoying flaw, as we'll see later.

I am a bit new to all this stuff, but I read a few guides and Reddit posts, so I'm aware of a few typical pitfalls and tried to avoid them in my test character card.

Essentially, the purpose of my test is to check how easy it would be for a newcomer to get started without much knowledge and fiddling around. So, I also left default model parameters offered by Backyard. I had to switch the Prompt Template though to avoid some terrible formatting issues with some models.

I tried to make the test prompt simple. I intentionally did not add any rules for creativity to see how creative the LLMs are by default.

I tried to avoid negative commands because they are known to have the opposite effect of filling the context with the ideas that the AI should not have. Also, I addressed the AI directly as "you" a few times and used bribe and threats technique to attempt to make it follow the rules better.

While simple, the prompt also has some traps to test how each model deals with specific ambiguities. I intentionally did reuse the same roleplay item (the key) to see if LLM keeps sticking to the order of events and does not start picking the events randomly just because they mention the key.

While testing, I did not use Author's notes and did not edit messages. But I regenerated a few messages to see if the model can come up with a better solution or keeps stuck with the wrong option only.

I tried to provoke the AI by using one-word replies (which it should not accept, according to my rules) and also by trying to make it talk by unrelated topics (which also was not allowed).

The test script test_character_card.txt and the chat logs for the models can be found in my GitHub repo: https://github.com/progmars/llm-sandbox The chat logs have my own comments marked with [].

Feel free to suggest improvements to the scenario, but keep in mind that it's supposed to be simple and not specific to any particular model, to test how they work by default.

Here are the main pitfalls that all models seemed to have:

- they had huge problems with following my rule to not accept one word responses. This often led to me answering just "yes" and the model happily considered that I have completed the action it requested. Boring. I really would like the model to ask explicit actions from me, like "Yes, I did unlock the door" and not just "ok".

- for some reason, they all tried to take the key from me and perform the action themselves, although every event description clearly stated that it is the user who uses the key always. I have no idea, how to stop them from blatantly taking over the control.

And now, finally, the winner is... llama2.11b.fimbulvetr-v2.gguf_v2.q5_k_m. It passed the test quite good, surpassing even Llama 3 based models with the same size, which was a surprise because I expected so much more from Llama 3. To be sure I did not just get lucky, I rerun the same script a few times, and fimbulvetr-v2 was pretty constant. It still tried to take the key from me a few times and it did let me through with single word replies, but it did that much less often than all the other models.

However, Fimbulvetr was dry as sand, all business, no environment descriptions, no actions, nothing. I modified my test (modifications are not included in the repo) to tell it to generate creative, imaginative responses with actions, such as *I scratch my beard* and *I rub my hands* in every message, but it did not work and Fimbulvetr was the driest of all the models I tried.

So, I'd really appreciate any tricks to unleash Fimbulvetr's imagination, or suggestions of any similar-sized models (but do not suggest ones that cannot handle at least 8k context reliably) that have the consistency of Fimbulvetr when it comes to following the rules and the roleplay event-based scenario.

When more RAM arrives next week, I'll test larger models. Also, I'll check the largest free (or even paid) Openrouter models with SillyTavern to see how much difference the size makes when it comes to following the rules.

So, that's it. Thanks for reading, if you had the patience :)

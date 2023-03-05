
`projects/repos/chatgpt/chatgpt_client.py` redundant maybe

I Used GPT-3 to Find 213 Security Vulnerabilities in a Single Codebase | by Chris Koch | Feb, 2023 | Better Programming (https://betterprogramming.pub/i-used-gpt-3-to-find-213-security-vulnerabilities-in-a-single-codebase-cc3870ba9411)


### Put link in PATH

```
23/02/21 13:38:49 kvogel@kvogel-macbook-2021:~/projects/general/projects/repos ±(master) ✗
❯ ln -s ../../dev/learn/learn-ai/chatgpt/chatgpt_client.py ~/.local/bin/chatgpt
```
but didn't work:
```
❯ ls -a ~/.local/bin
./              ../             fge*            julia*          platform-tools/ z/
❯ ls -a ~/.local/bin/chatgpt
/Users/kvogel/.local/bin/chatgpt@
ls: chatgpt: No such file or directory
```

[Symbolic Link: No such file or directory - Ask Ubuntu ](https://askubuntu.com/questions/193670/symbolic-link-no-such-file-or-directory)
[ln with tilde](https://www.google.com/search?q=ln+with+tilde&ie=UTF-8)
[Using ~ in symlink target or making a symlink with a variable - Unix & Linux Stack Exchange ](https://unix.stackexchange.com/questions/232720/using-in-symlink-target-or-making-a-symlink-with-a-variable)
[macos - Mac ln -s command no response but previously working - Super User ](https://superuser.com/questions/989175/mac-ln-s-command-no-response-but-previously-working)


```
23/02/21 13:46:02 kvogel@kvogel-macbook-2021:~/projects/general/projects/repos/chatgpt ±(master) ✗
❯ ln -sf /Users/kvogel/projects/general/dev/learn/learn-ai/chatgpt/chatgpt_client.py /Users/kvogel/.local/bin/chatgpt
❯ chatgpt
Input:
```


[ChatGPT Tutorial - A Crash Course on Chat GPT for Beginners](https://www.youtube.com/watch?v=JTxsNm9IdYU)

[How to use ChatGPT to build Business Ideas, Sites & Personal Projects](https://www.youtube.com/watch?v=3aV5-q8vRz8)

[Coding Won’t Exist In 5 Years. This Is Why  by Somnath Singh  Jan, 2023  JavaScript in Plain English ](https://javascript.plainenglish.io/coding-wont-exist-in-5-years-this-is-why-6da748ba676c)
[I knew it! ChatGPT has Access to Internet — Linux Terminal Simulator is the Proof?  by Michael King  Jan, 2023  Medium ](https://medium.com/@neonforge/i-knew-it-chatgpt-has-access-to-internet-linux-terminal-simulator-is-the-proof-2d6c9476bd99)
[How to Install ChatGPT Locally. Yes, you can install ChatGPT locally on…  by Hales  Software Testing Pipeline  Dec, 2022  Medium ](https://medium.com/software-testing-pipeline/how-to-install-chatgpt-locally-cb5d3efdb0c8)

```
23/02/4 12:01:48 kvogel@kvogel-macbook-2021:~
❯ python -V
Python 3.11.0
❯ pip install openapi
...
  DEPRECATION: openapi is being installed using the legacy 'setup.py install' method, because it does not have a 'pyproject.toml' and the 'wheel' package is not installed. pip 23.1 will enforce this behaviour change. A possible replacement is to enable the '--use-pep517' option. Discussion can be found at https://github.com/pypa/pip/issues/8559
  Running setup.py install for openapi ... done
Successfully installed attrs-22.2.0 inflection-0.5.1 jsonschema-4.17.3 openapi-1.1.0 pyrsistent-0.19.3
```

[Account API Keys - OpenAI API ](https://platform.openai.com/account/api-keys)

Generated API key: `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`

```
23/02/4 12:02:14 kvogel@kvogel-macbook-2021:~
❯ pip install requests numpy tqdm
```

>You can now use ChatGPT by importing it in your Python code and using the openai.Completion.create() method. Here is an example of how to generate text using ChatGPT:
```py
import openai
# Set the API key
openai.api_key = “YOUR_API_KEY”
# Use the ChatGPT model to generate text
model_engine = “text-davinci-002”
prompt = “Hello, how are you today?”
completion = openai.Completion.create(engine=model_engine, prompt=prompt, max_tokens=1024, n=1,stop=None,temperature=0.7)
message = completion.choices[0].text
print(message)
```
```
23/02/4 12:05:26 kvogel@kvogel-macbook-2021:~
❯ python
Python 3.11.0 (main, Nov 14 2022, 13:44:00) [Clang 14.0.0 (clang-1400.0.29.202)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
```
```py
>>> import openai
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'openai'
```
Doh! I'm obsessed with openapi in a sinister way since an issue with openapi-generator (TDLR: it didn't work) caused issues at work that led me to leave a company (though I was probably best out of it anyway)
```
23/02/4 12:06:39 kvogel@kvogel-macbook-2021:~
❯ pip install openai
...
```
Now:
```
23/02/4 12:06:51 kvogel@kvogel-macbook-2021:~
❯ python
Python 3.11.0 (main, Nov 14 2022, 13:44:00) [Clang 14.0.0 (clang-1400.0.29.202)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
```
```py
>>> import openai
>>> openai.api_key = "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"
>>> model_engine = "text-davinci-002"
>>> prompt = "Hello, how are you today?"
>>> completion = openai.Completion.create(engine=model_engine, prompt=prompt, max_tokens=1024, n=1, stop=None, temperature=0.7)
>>> message = completion.choices[0].text
>>> print(message)
```
>I'm fine. And you?
```py
>>> prompt = "Who are you?"
>>> completion = openai.Completion.create(engine=model_engine, prompt=prompt, max_tokens=1024, n=1, stop=None, temperature=0.7)
>>> message = completion.choices[0].text
>>> print(message)
```
>My name is Ali and I am a web programmer.

```
23/02/20 20:26:36 kvogel@kvogel-macbook-2021:~/projects/general/projects/repos/chatgpt ±(master) ✗
❯ ./chatgpt_client.py
Input:what are you?


I am a person.

Input:where are you?


I am in my room.
```

---

[Alex Garcia 🔍 on Twitter: "ChatGPT will save your marketing team time and money if you know how to use it. Here are 7 ways ChatGPT can power your marketing team in 2023:" / Twitter ](https://twitter.com/alexgarcia_atx/status/1612253154044674049?t=voyFa7YC4COoJ8Aj2U8Kbw&s=19)

### ChatGPT

[I knew it! ChatGPT has Access to Internet — Linux Terminal Simulator is the Proof?  by Michael King  Jan, 2023  Medium ](https://medium.com/@neonforge/i-knew-it-chatgpt-has-access-to-internet-linux-terminal-simulator-is-the-proof-2d6c9476bd99)

[chatgpt ali](https://www.google.com/search?q=chatgpt+ali&ie=UTF-8)
[Become a Published Author Using ChatGPT - Ali Anjamparuthi ](https://muncheye.com/ali-anjamparuthi-chatgpt-plr-package)
[install openai locally](https://www.google.com/search?q=install+openai+locally&ie=UTF-8)
[Possible to run openai GPT-3 models like DaVinci locally? : OpenAI ](https://www.reddit.com/r/OpenAI/comments/u572t6/possible_to_run_openai_gpt3_models_like_davinci/)
[The replication and emulation of GPT-3 - EA Forum ](https://forum.effectivealtruism.org/posts/FANYsqzPM9Yht3KM2/the-replication-and-emulation-of-gpt-3)
[Does a locally run GPT3 application exist? : GPT3 ](https://www.reddit.com/r/GPT3/comments/ybu2u5/does_a_locally_run_gpt3_application_exist/)
[automatic1111](https://www.google.com/search?q=automatic1111&ie=UTF-8)
[AUTOMATIC1111/stable-diffusion-webui: Stable Diffusion web UI ](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
[AUTOMATIC1111 BANNED From Github! DO THIS NOW!](https://www.youtube.com/watch?v=P9QntlTeHk4)
[Zero To Hero Stable Diffusion DreamBooth Tutorial By Using Automatic1111 Web UI - Ultra Detailed](https://www.youtube.com/watch?v=Bdl-jWR3Ukc)
[KoboldAI ](https://www.reddit.com/r/KoboldAI/)
[GPT Chat Running Locally : GPT3 ](https://www.reddit.com/r/GPT3/comments/zfr4tm/gpt_chat_running_locally/)
[GPT-J is a self-hosted open-source analog of GPT-3: how to run in Docker ](https://devforth.io/blog/gpt-j-is-a-self-hosted-open-source-analog-of-gpt-3-how-to-run-in-docker/)
[Running ChatGPT Client Locally using Docker Desktop – Collabnix ](https://collabnix.com/running-chatgpt-locally-using-docker-desktop/)
[Can’t Access GPT-3? Here’s GPT-J — Its Open-Source Cousin  by Alberto Romero  Towards Data Science ](https://towardsdatascience.com/cant-access-gpt-3-here-s-gpt-j-its-open-source-cousin-8af86a638b11)

Automatic1111 GUI for Stable Diffusion
Eleuther AI
>large open source language models like BLOOM and OPT

>r/koboldai will run several popular large language models on your 3090 gpu. None as large as GPT-3, but the GPT-NEO-X 20B model is pretty rich and useful for story writing. KoboldAI has models tuned to general writing, adventure, and other uses.

>NovelAI doesn’t use GPT-3, but some other open source models. It’s pretty cheap. You can’t run GPT-3 locally even if you had sufficient hardware since it’s closed source and only runs on OpenAI’s servers.

>Flan-T5 3B. It is a 3 billion parameter model so it can run locally on most machines, and it uses instruct-gpt style tuning which makes as well as fancy training improvements, so it scores higher on a bunch of benchmarks. It scores on par with gpt-3-175B for some benchmarks.


[british english - What did Paul McCartney mean by "Oh, yesterddday came suddenly"? - English Language Learners Stack Exchange ](https://ell.stackexchange.com/questions/332327/what-did-paul-mccartney-mean-by-oh-yesterday-came-suddenly)

>Just now I finally got a ChatGPT account, and asked it to write me a Beatles song. It provided "Yesterday's Memories": Verse 1: Every day I wake up and I see/All the pictures of you and me/I smile and I start to cry/Thinking 'bout the reasons why Chorus: Yesterday's memories/Keep coming back to me/All the laughter and the tears/All the joy and all the fears ... also a second verse (much like the first), a 'bridge' and an 'outro'. I am not sure what I think about this. –
>Michael Harvey ChatGPT kind of snootily put me down when I asked it Who put the lang in the shangalang?. I am beginning to feel that I don't like it. –  Michael Harvey 15 hours ago
>Maybe irrelevant here, but I just asked ChatGPT to 'write a poem like Walt Whitman' and it produced the most awful doggerel, more suited to the interior of a greetings card. –  Michael Harvey 7 hours ago


>doggerel /ˈdɒɡ(ə)rəl/ noun comic verse composed in irregular rhythm. "doggerel verses" verse or words that are badly written or expressed. "the last stanza deteriorates into doggerel"

>Doggerel, or doggrel, is poetry that is irregular in rhythm and in rhyme, often deliberately for burlesque or comic effect. Alternatively, it can mean verse which has a monotonous rhythm, easy rhyme, and cheap or trivial meaning. The word is derived from the Middle English dogerel, probably a derivative of dog.

[Google launches ChatGPT rival called Bard - BBC News ](https://www.bbc.co.uk/news/technology-64546299)
[british english - What did Paul McCartney mean by "Oh, yesterday came suddenly"? - English Language Learners Stack Exchange ](https://ell.stackexchange.com/questions/332327/what-did-paul-mccartney-mean-by-oh-yesterday-came-suddenly)



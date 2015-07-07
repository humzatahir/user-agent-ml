# Detect bots from user agent strings
User-agent-ml detects whether a user agent string refers to a bot or 
to a legitimate browser. The method is hybrid: it is based on rules and machine
learning. The rule based part allows for high efficiency since most bot hits
come from well known sources (e.g., search engines), and the machine learning 
part allows detection of less well known user agent strings or new ones, which 
it would have been hard to capture with a solely rule based system. 

## Usage
```python
import user_agent_ml
uaml = user_agent_ml.user_agent_ml("../data/user-agent.model")
uaml.predict("Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_4) AppleWebKit/600.7.12 (KHTML, like Gecko) Version/8.0.7 Safari/600.7.12")
>>> False
```
The `.predict("user-agent-string")` funtion returns `True` is the user agent
string is identifed as bot, and `False` is the string is identified as a regular
browser. The accuracy (measured in F1-score) of the current model is 99.50% (±
0.0187).


## Acknowledgements
User-agent-ml is based on the data from the project
[MAUL](https://github.com/bholley/maul), and project
[NERD](https://github.com/larsmans/nerd) for the skeleton of the machine
learning framework. The development of user-agent-ml was partially supported by
[Europeana](http://europeana.eu), the European Cultural Heritage Search Engine.
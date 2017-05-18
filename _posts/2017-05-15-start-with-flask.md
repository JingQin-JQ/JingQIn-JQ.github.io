---
layout: post
title: Learning Flask by trying it

tags: 
- Flask Study
---
Flask is a web development tool in python. Here I would like to learn it by built a small server for my self.

### Quick start
Here is a piece of very first flask python code. This is a piece code from Welcome | Flask (A Python Microframework)
<http://flask.pocoo.org/docs/0.12/quickstart/> : 

```python
from flask import Flask #imported the Flask class

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__ == "__main__": # where to start
    app.run() 
```
Simply running Then we have http://127.0.0.1:5000/ printed "Hello World!"

```
python hello.py
 * Running on http://localhost:5000/
```

route() decorator to tell Flask what URL should trigger our function.
The function is given a name which is also used to generate URLs for that particular function and returns the message we want to display in the user’s browser.

So, now we have a simple but working server for ourselves. Next step is to add our own message into it.

But before that, we need to open the "Debug" mode:

### Debug
If you enable debug support the server will reload itself on code changes, and it will also provide you with a helpful debugger if things go wrong.
Just add "debug=True" to your function as a parameter.

```python
app.run(debug=True) 
```
you will see your **http://localhost:5000/** as this if you have bugs in your code.

![Alt Image Text](http://flask.pocoo.org/docs/0.12/_images/debugger.png "Type Error")

### route
Route can be changed, just like a website have several pages, you can also make multiple pages by write multiple route. Every page will show different information as you wanted.

```python
@app.route('/')
def index():
    return 'Index Page'

@app.route('/hi')
def hello():
    return 'Hello, World'
```

Now, let's have fun!
I want the page shows some text which will respond to my input!
	
### Variable Rules
Flask uses \<variable_name>  to pass a keyword argument to your function. And you can return something by using this argument.

```python
@app.route('/app/<name>/<age>')
def compare(name=None, age=None):
    if (name is None) or (age is None):
        return "message not complete!"
    else:
    	return '%s years old %s is online now!' % (age, name)
```

### Real function:
I have written a small code to give a list of coupon codes. Now I would like to put this code on my server, to provide coupon codes, I will take the numbers of coupon code and the length of code from \<variable_name>.

Here is my code to do it:

``` python
from flask import Flask 
app = Flask(__name__)

import random

@app.route('/app/<number>/<length>')

def coupon_maker(number, length):
    coupon = []
    for i in range(int(number)):
        coupon.append(''.join([random.choice('ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789') for _ in range(int(length))]))
        print "coupon[",i,"]:",coupon[i]
    return str(coupon)
    
if __name__ == '__main__':
    app.run(debug=True)
```    
When I want to have 4 codes, that have 6 characters in each of them, it prints coupon codes on the page:<http://127.0.0.1:5000/app/4/6> as: 

['6M6M6C', '9OZO83', '631U59', 'C614XA']

and print on the shell,as:

coupon[ 0 ]: 6M6M6C

coupon[ 1 ]: 9OZO83

coupon[ 2 ]: 631U59

coupon[ 3 ]: C614XA

#### Yeah!!  It works!!

At last, I want to show it to my roommate, I need it also works on my home-LAN.

### Be visible across the network

This can be easilly done by add a parameter to my app.run(). By default it runs on localhost, change it to app.run(host= '0.0.0.0'), it will run on my machines IP address.

```python
app.run(host='0.0.0.0', debug=True)

### Now I can take it to show off!!


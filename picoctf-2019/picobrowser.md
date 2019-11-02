# The Challenge

[This website](https://2019shell1.picoctf.com/problem/32205/) has a button you
can press that will give you the flag. However, if you press it in your web
browser, it will give you an error saying "You're not picobrowser!" and list
some text after it that depends on your OS and browser (for me, it says
`Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:70.0) Gecko/20100101 Firefox/70.0`,
but yours will likel be different).

That string of text is known as a
[User-Agent](https://en.wikipedia.org/wiki/User_agent) and it tells the server
what browser you're using.

To convince them that you're running pico browser, you can just change your
user-agent string. To do this, I chose to use `curl` because it easily allows
you to control the headers. You need to run

```bash
curl --user-agent "picobrowser" "https://2019shell1.picoctf.com/problem/32205/flag"
```

And then buried in the output, you'll see the flag.


# Colab Tricks

## Colab SSH

Run [this notebook](ColabSSH.ipynb), changed the metadata to have a P100 and 25GB RAM.

- Requires an `ngrok` login
- Kill `nrgok` in the end.

In your terminal, <port> from the [ngrok auth website](https://dashboard.ngrok.com/auth)

```
ssh root@0.tcp.ngrok.io -p <port>
```

- Password lies in the Colab Notebook itself
- Jupyter Notebook through SSH

```
jupyter notebook --no-browser --port=7009 --ip 127.0.0.1
```

- In Local Machine, use `lsof -ti:8888 | xargs kill -9`, if port isn't responding

```
ssh -N -f -L localhost:8888:localhost:7009 root@0.tcp.ngrok.io -p <port>
```

Optional(but highly recommended to use GNU Screen, VIM)

```
apt-get install screen
apt-get install vim
```
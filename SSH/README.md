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

- If the command `nvidia-smi` doesn't work, run this
```
export LD_PRELOAD=/usr/lib64-nvidia/libnvidia-ml.so
```

Optional(but highly recommended to use GNU Screen, VIM)

```
apt-get install screen
apt-get install vim
```

For Conda Env

```
wget https://repo.anaconda.com/miniconda/Miniconda3-py37_4.8.2-Linux-x86_64.sh
chmod +x Miniconda3-py37_4.8.2-Linux-x86_64.sh
bash ./Miniconda3-py37_4.8.2-Linux-x86_64.sh -b -f -p /usr/local
```

```
import sys
sys.path.append('/usr/local/lib/python3.7/site-packages/')
```

```
conda init bash
<REQUIRES A RESTART OF THE TERMINAL>
conda activate
```
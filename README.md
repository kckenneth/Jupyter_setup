|Title |  Jupyter Installation |
|-----------|----------------------------------|
|Author | Kenneth Chen |
|Utility | Jupyter Notebook, Python |
|Date | 10/08/2018 |

# Jupyter Notebook, Pyspark

In order to answer question 6 to 10, I thought of analyzing moby10b.txt in pyspark. So I need to install python in Centos OS first. First Centos also has its own software collection. To install those, I first need to install SCL release (Software Collection). 

```
# sudo yum install centos-release-scl
# sudo yum install rh-python36 bzip2 pyspark
# python --version

Python 2.7.5
```

Since python 2.7.5 is the default version, we will update the version by bash. 
```
# scl enable rh-python36 bash
# python --version

Python 3.6.3
```

### Setting up Jupyter Notebook

You need to set up the configuration file for jupyter notebook to work in your browser. Remember, you're launching jupyter-notebook from the server. But you will get access to jupyter-notebook from your local machine browser. Jupyter requires Python 2.7 or 3.5 and higher. 

If you have python2
```
# pip install --upgrade pip
# python -m pip install --upgrade pip
# python -m pip install jupyter
```
For python3
```
python3 -m pip install --upgrade pip
python3 -m pip install jupyter
```
You need to have a jupyter configuration file. 
```
# jupyter notebook --generate-config

Writing default config to: /root/.jupyter/jupyter_notebook_config.py
```
Modifying the configuration file
```
# cd /root/.jupyter/
# vi jupyter_notebook_config.py
```
Copy the following script and paste it the jupyter_notebook_config.py
```
c = get_config()
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False
c.NotebookApp.port = 8123
```
Launch jupyter-notebook with IP bind
```
# jupyter-notebook --ip=50.97.252.101 --allow-root
```


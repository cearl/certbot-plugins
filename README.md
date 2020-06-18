# certbot-plugins
just some plugins I wrote for certbot

Installing and using these plugins

make a setup.py (this one is for the netscaler plugin)

from setuptools import setup


setup(
    name='netscaler',
    package='netscaler.py',

    install_requires=[
        'certbot',
        'zope.interface',
    ],
    entry_points={
        'certbot.plugins': [
            'netscaler = netscaler:Installer',
        ],
    },
)


put this in the same folder as the netscaler.py file 

1) install certbot 
2) pip install -e folderName/ to install the local code
3) run: certbot plugins and make sure its in the list
4) Request cert with " certbot -i netscaler -a infoblox -d domain.com" -a being the Authenticator and -i being the installer
5) add a cron job to run "certbot renew" daily

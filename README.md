# Eventex

Sistema de eventos encomendado pela Morena.

[![Build Status](https://travis-ci.org/fplucas/eventex-fplucas.svg?branch=master)](https://travis-ci.org/fplucas/eventex-fplucas)
[![Code Health](https://landscape.io/github/fplucas/eventex-fplucas/master/landscape.svg?style=flat)](https://landscape.io/github/fplucas/eventex-fplucas/master)

## Como desenvolver?

1. Clone o repositório.
1. Crie um virtualenv com Python 3.5
1. Ative o virtualenv.
1. Instale as dependências.
1. Configure a instância com o .env
1. Execute os testes.

```console
git clone git@github.com:fplucas/eventex-fplucas.git wttd
cd wttd
python -m venv .wttd
source .wttd/bin/activate
pip install -r requirements.txt
cp contrib/env-sample .env
python manage.py test
```

## Como fazer o deploy?

1. Crie uma instância no heroku.
1. Envie as configurações para o heroku.
1. Defina uma SECRET_KEY segura para a instância.
1. Defina DEBUG=False
1. Configure o serviço de email.
1. Envie o código para o heroku

```console
heroku create minhainstancia
heroku config:push
heroku config:set SECRET_KEY=`python contrib/secret_gen.py`
heroku config:set DEBUG=False
# configuro o email
git push heroku master --force
```
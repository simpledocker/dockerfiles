FROM simpledocker/python3-psycopg2-binary

ADD requirements.txt /tmp/requirements.txt

RUN python3 -m pip install -r /tmp/requirements.txt && rm /tmp/requirements.txt

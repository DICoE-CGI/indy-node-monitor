FROM bcgovimages/von-image:next-1

USER root

ADD requirements.txt .
RUN pip3 install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

ADD networks.json .
ADD *.py ./
RUN mkdir /home/indy/plugins
RUN chmod 777 /home/indy/plugins
RUN mkdir /home/indy/conf
RUN chmod 777 /home/indy/conf
RUN mkdir /home/indy/logs
RUN chmod 777 /home/indy/logs

ENTRYPOINT ["bash", "-c", "python main.py $@", "--"]
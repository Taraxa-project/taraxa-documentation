# Performing a Data Reset

### How to reset your node's data

During the testing period, we will also make changes on the protocol level and you will have to re-sync all the data. Don't worry, we will let you know. To remove the current data and do a full re-sync you have to run the following commands:

{% tabs %}
{% tab title="Windows" %}
```text
cd .\Desktop\taraxa-ops-master\taraxa_compose\
docker-compose down -v
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Mac" %}
```text
cd ~/Desktop/taraxa-ops-master/taraxa_compose
docker-compose down -v
docker-compose pull
docker-compose up -d
docker-compose logs -f
```
{% endtab %}

{% tab title="Linux" %}
```
cd ~/taraxa-ops-master/taraxa_compose
sudo docker-compose down -v
sudo docker-compose pull
sudo docker-compose up -d
sudo docker-compose logs -f
```
{% endtab %}
{% endtabs %}

### Checking that the reset worked




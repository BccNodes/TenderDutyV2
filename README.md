TenderDuty v2

Tenderduty, Tendermint zincirleri için kapsamlı bir izleme aracıdır. Birincil işlevi, blokların eksik olması durumunda bir doğrulayıcıyı uyarmaktır ve diğer birçok özelliğe sahiptir.

# Docker ile Kurulum

`curl -fsSL https://get.docker.com | sh`

# Yapılandır

```mkdir tenderduty && cd tenderduty```

```docker run --rm ghcr.io/blockpane/tenderduty:latest -example-config >config.yml```

*config.yml* dosyasını düzenleyin zincirler, bildirim yöntemleri vb. ekleyin.

```docker run -d --name tenderduty -p "8888:8888" -p "28686:28686" --restart unless-stopped -v $(pwd)/config.yml:/var/lib/tenderduty/config.yml ghcr.io/blockpane/tenderduty:latest```

```docker logs -f --tail 20 tenderduty```

# Gösterge Paneli

Node durumunu görüntülemek için `http://SUNUCU_IP_ADRESİNİZ:8888`

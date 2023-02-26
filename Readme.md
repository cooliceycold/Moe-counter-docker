# Moe-counter

多种风格可选的萌萌计数器,源项目地址[journey-ad/Moe-counter](https://github.com/journey-ad/Moe-counter),本项目进行了Docker化，技术不佳，请见谅。

![Moe-counter](https://count.koalarong.com/get/@Moe-counter.github)

<details>
<summary>More theme</summary>

##### asoul
![asoul](https://count.koalarong.com/get/@demo?theme=asoul)

##### moebooru
![moebooru](https://count.koalarong.com/get/@demo?theme=moebooru)


## Demo
[https://icecf.cf/](https://icecf.cf/)

## Usage

### Compose示例

```bash
 moe-counter:
    image: koalarong/moe-counter:latest
    #ports:
      #- "3000:3000"
    restart: always
    container_name: docker-moe-counter
    networks:
      - webapp
    volumes:
      - ../data/moe-counter/count.db:/usr/local/src/Moe-counter/count.db
#使用sqlite请将count.db文件放置于宿主机，挂载于容器中，以防止容器重建时丢失数据
```

### Nginx反代示例

```bash
location /get/ {
        proxy_pass http://docker-moe-counter:3000/get/;
        proxy_set_header Host $host:$server_port;
  }
```

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

### Nginx反代示例

```bash
location /get/ {
        proxy_pass http://docker-moe-counter:3000/get/;
        proxy_set_header Host $host:$server_port;
  }
```

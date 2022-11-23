## Proje 1
- Dotnet SDK 6'yı base image alarak, içinde sadece fortify yüklü, bu projenin dosyaları içinde olmayacak şekilde bir imaj yaratın.
- Yaratılan imajı <dockerhub kullanıcı ismi>/fortify:dotnet ismiyle dockerhub'a yükleyip, private'a çekin.
- Bu imaj aşağıdaki gibi çağırıldığında, buna benzer bir sonuç vermeli. 

```
docker run --rm -it <dockerhub kullanıcı ismi>/fortify:dotnet /opt/Fortify/Fortify_SCA_and_Apps_22.1.1/bin/sourceanalyzer

Fortify Static Code Analyzer 22.1.1.0017
Copyright (c) 2003-2022 Micro Focus or one of its affiliates

For command-line help, type 'sourceanalyzer -h'
```


## Proje 2
- Bu projeyi kendi github kullanıcınızla fork'layın.
- Lokalde bir sunucuya github worker'ı kurun.
- İstediğimiz komutlar daha önce yarattığımız docker imajı içinde çalışacak şekilde, bir github pipeline'ı hazırlayın.
  https://docs.github.com/en/actions/using-jobs/running-jobs-in-a-container (container içinde çalıştırma örnek yml)
- Bu pipeline içine proje dosyalarını çekin ve fortify'la tarayın.
- Çıkan sonucu otomatik olarak, ssc'ye yükleyin. Token veya password yml dosyasında hardcoded olmamalı.


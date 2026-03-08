# Домашнее задание к занятию "`Gitlab`" - `Смирнов Максим`


### Задание 1

`С Vagrant вариант не заработал по причине того, что конфигурация ноутбука не поддерживает вложенную виртуализацию. Отключение hyper-V не помогло, равно как и настойки Bios и тд. Вариант с локальной установкой тоже завести не удалось. localhost никак не детектировался, ни в браузере, ни curl запросом достучаться до gitlab не удавалось. В итоге только развертывание на облачной машине и доступ по IP сработал`

`Пустой репозиторий после клонирования`
![img/scr1-empty_repo_.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr1-empty_repo_.jpg)

`Параметры runner`
![img/scr2-runner_props.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr2-runner_props.jpg)

`Runner online`
![img/scr3-runner_online.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr3-runner_online.jpg)
 
---

### Задание 2

`Потребовалось много итераций чтобы заработал build но в итоге получилось`

```
.gitlab-ci.yml...
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.21
  script: 
   - go test .
  tags:
   - NetologyStudy

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
  tags:
   - NetologyStudy
```

`Файл .gitlab-ci.yml зарушен в проект`
![img/scr1-empty_repo_.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr1-empty_repo_.jpg)

`Отработал test`
![img/scr2-runner_props.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr2-runner_props.jpg)

`Отработал и build`
![img/scr3-runner_online.jpg](https://github.com/turboturtle-90/homework_template/blob/cc21548516789db38e9b175ca51359b0b38af7d4/img/scr3-runner_online.jpg)


---

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

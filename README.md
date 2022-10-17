<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## Setup dockerizado de laravel 9 com nginx, php 8.1, composer, redis, mysql 5.7

setup feito para ser usado em produção com o mínimo necessário.


## O que você irá encontrar aqui?
- imagens personalizados do php 8
- containers em uma mesma rede sem precisa expor algumas portas de alguns serviços em produção
- configuração do nginx
- configuração do php
- configuração do redis
- configuração do mysql e passando argumentos (username, password)
- configuração de volume para você não perder seus dados que têm ser persistindos no banco da tua máquina e não somente do modo "virtual"
- configuração para permitir o usuário do sistema instalar tudo que ele queira sem frescuras de ter que depois usar chmod/chown ou coisas do tipo
- ordenação de funcionamento de containers (container de fila precisa antes do container redis funcionando, então o arquivo se encarrega de subir primeiro o redis e depois a fila)
- containers sempre restartando automaticamente quando eles cairem por algum motivo
- container responsável por rodar certos comandos, por exemplo, o container de fila precisa de um comando para ser startado, então, eu delego ao container a função de sempre rodar o comando "php artisan queue:work" para as filas do laravel funcionarem.

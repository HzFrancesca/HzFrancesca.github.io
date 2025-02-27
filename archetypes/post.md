---
date : '{{ .Date }}'
draft : true
title : '{{ replace .File.ContentBaseName "-" " " | title }}'
description: 'A simple introduction'
image : 'choose a image to place at the top of article'
categories : 
    - category1
    - category2
tags : 
    - tag1
    - tag2
---
---
layout: post
title:  "Mobaxterm setting for aws with jupyter @ Win"
date:   2018-10-23
background: '/img/posts/skt.jpg'
categories: post
---

AWS의 Junpyter Notebook 사용을 위한 Mobaxterm 설정 
================================================================

- 본 설명에서는
  * Mobaxterm에서 Window의 Directory 접근 설정을 포함한다.
  * Mobaxterm을 통해 aws에 용이한 접근을 위해 ssh option을 local terminal을 통해 제어하는 것을 포함한다.

Mobaxterm의 Local Terminal에서 Window Device의 Directory를 접근하려면...
------------------------
* Step 1: Mobaxterm의 셋팅을 클릭.
![step1](https://lh3.googleusercontent.com/ewqYZVNjMzYMvUQ1PbPft3DDT4iX-K93NzKaF1QsYI662CY-EChKI79x6SHXwOE7mFUcmUdMrCEGfrTAJqt0uaXSac5SLUhGqOaA3LCuLkWQ4bY7tn31wfAIocpZqWR91c63FXwt6dj1u-xLU0DD9Kki8MlPoPDYWGvjLfrfU5_5uUeFrt6aW-EwecQ869DxSnSWJQbi6-1-JjJ5KB9YuADZr8LRLNhRAbOf6xXZ0c9Q6WiYOCXEEzYeN2EAHoFipaJLkWjH4SNiXJ67jZ8KUXTjycYW5NjNKwde6v8fhtmzBPs0fKnQgdlmO74_x5maYMvyI2WLDQzN_2mckQduB8awO__rJrqHlEOijFxxk7pM4QEOKHj6M71Ufw-ynAJZGb9-01w_kOwB-vktFU_OWXsh3qBRuoDcxJ-VqKxjj-tJ4h2bXfC2wZT-3FEdpit5fp_u6-npFxGw3cjQO6ej1PdimE8AohvOwgQU7JXYV_l6EbArC0ZTWrNNUXlPD3qDNDVPkJ14M4lsv0qJyOG5w56DJL16i8QJRTEUY1tuXWb1uxjzTgbHSCaMFaB5tfgcnKcsFnCsY1AhYxi7UiNYJVktRmDcuJ-0ji1PzGyQXTOnH2SN37qvfq6eAeCmqdgs=w1026-h513-no)
* Step 2: Use Window blah blah blah check.
  * Window Path를 써야 AWS의 private key 위치에 접근이 가능함.
![step2](https://lh3.googleusercontent.com/wgezyaCB98HB1LMyFGYuYXtUzHvGVakC87muH2jQmZQs8Jc3qM43uMpXZQ9fCIm4FLevQQg3n5IIr-PAey4NOHueGPfVIxpGvNcfX5zwFiSsumPWWZ4H7PzYeZmLfwy3zbvUNlrvur-s0Jwt47rFT-CpdcoRL2K44SNcRbnk3GUJxmt6bbCOJOaF0R6QeEFdri3q00YR1CH3VpFfeQmb2eHeOy2cu5vJqSc-S05JeHDWZ6fKHfSTkxZAnY7l3i-zccp_HYL2BTOLOHO2Pof9akAnHYoPdIsNK1f9pcxD9P48DB03Cak1UmdYF_w7QwlrUzs4N6_ODyITc6Y7jVpojCA48yuXrHDBXJwg_cSvzFtAbCkwgTmV4_GQb4EjVNZE1zMmq4qWWfweo6i9vgS0gIDJQc5YUGLUoJYPu38D6rASJ92DqvMV7GqGgy4k_zc73g3YqkwGE5NLoh-cdUcuEQadHjal9V2ouw8zT6TRCMJPV3294FsLvUe928iFqTzYW_asMwYky6yz4V74iUytxPL-bexEVilx_h38WkOB3xo1_gqvpypfD02Ah5NyJiAazfcVTgKo4ZyGOM9rNQCBYZc9NpsN5Bac6EvAAlDxB_FsMSH1LERu-WR7ZwmKEkQ4=w593-h330-no)
* Step 3: Local Terminal Click
![step3](https://lh3.googleusercontent.com/tnB29myh329yBH5TaiCfA2c28xR_mwtNBcBpAGr3PaSpYrmeLro9ZOlroeQAcxmw9RHFLR_rCWAkRziHbn88hCdrVY2rryPTbHcOjPKSmebveXYBS9CeQh8lxBw6HD0GxQv7APbg8jg9X16Oh4HSEyxO1nvQb4a84F44rjg36-EidZq0DNtN5xEpw3ikVYD6mjL_bmEPgAhNWVHnzB-F-KITmSL5n7eNGIgi5zPb3vmKDWZpT-9YoHGBQBuwyhhafBQlma4spq2EOPSlqreLv6fZTz2rBW98RlOKnCgI86Oj1TPgrm71KNt1Ylip6ryMXYd0v0FM4objo5wWI8G2v1I0tXYC_yravz_d6AQ171HOdOyZ62LTL4J61yfGucljvOsW_wxWXpxlDg4oU865PHyJwHstPWgEYKq_L0hRcDOTjxla0GB4gx2JMwP8VQCNg3838zsVhECBeVlVASRm0sPKwTfBSKNHKSmneE__BX4MMQL8lkAOlNRQ1R0cUydCRmgZjWi961UyhZaH36xNQRj9yd2GCuXocyJJtD64pgwwN8f3OFBPChWyCgtOJ01izsBn6uMJK0EbhTgNvUD3nXqxilkKlYuo0kmAwg-erCPCC3AgQa8YvjnUTxaM3AzEN8nv0__RVtUYyw2jMFzeATuYMjhWyAZyMmgWkGzEW32z_mLU8ER6rUI1cQ=w567-h391-no)
* Step 4: ssh 접속
  * Local Terminal을 통해서 Jupyter Notebook의 port forward가 가능함
![step4](https://lh3.googleusercontent.com/wku85NQi5TjrI3ZFB6E5CMKuqK5G-e7Lwk4wUIWMJAc69bCP9nqC_w6q470s107J1tFkjWeTuaEQH8OnjuFmA_54g70nPz-ddM18AQJQnxs6wZkpyyobfrCNN8ky8bMTmAjhP7jI9IozA_fdkSAXQd8tvv8KwQtM-bA0Qsipaa_YiTXsVS-VQWWrYv763mFCcGbynK4tMWcDQ2Vqfm1Be04ImN_Hxub01Oh_wXOLnpYYfKTvehLxyG1kmMz8EerA4SmyJ8R5JIxUJEyEaE_Ml_taeTYY64emGB6WqJ2tLoRUlqrI1Qc_ToR3YbZJYAfqB9Saghv5UjWb3xSEmeuqr3C4mJVAfpQCZvyvDomKL454CrnnMAdkzTZh3ppEvVc93t8pzOo7F0YdVDy7wjSZytnLP4ssSXJ2Cs5r4eMx-m7rBL8lWxsvlwyHvpHESrvKeTvUlrwe85JA9FzoeThyRcrtCwqVyzECj2wktmF4A8y92ua18oaIqxYKobApwBZ3Hx1K-Ne5Pwn2xNpV7HRqPgM7epR33OwcFORZUKRRAjN909zZEX_7hLBAqL8bv0qP3lQSuYfblywOxhuDu3rLcEIDLx4ZrewHd_AvXoIwhMAmSxtFHnLSJCNcFqBZiooDHG0jDmCr6ERb7s2AaiH7MOHEyq-2B5s3oVrch0_Oi7Z6qQD97Jxhx0Bm2w=w805-h236-no)

Code 동작 환경
------------------------
* OS: Ubuntu 16.04 64bit
* 개발환경: python2.7
* 관련 dependency
  * sudo apt-get install python2.7-dev python-pip
  * sudo pip install -U pip==9.0.3
  * sudo pip install jupyter
  * sudo apt-get install libopencv-dev python-opencv
  * sudo pip install matplotlib

만약 Ubuntu 환경이 없다면
------------------------
* AWS (Amazon Web Service)를 통해 환경을 무료로 제공 받을 수 있다.
  * [AWS사용설명서](https://drive.google.com/open?id=1oDysftiGrr3yo3qX1jfLJmiRu8xhiNRd62tjk5LvdgQ)

AWS 실습 환경 사용 방법
------------------------

* 접속 방법
~~~
$ ssh -i /path/to/your_key.pem -L 8888:127.0.0.1:8888 ubuntu@your.aws.ip.add 
~~~
ex:
~~~
$ ssh -i ~/Downloads/skt_lecture.pem -L 8888:127.0.0.1:8888 ubuntu@52.79.44.222 
~~~

* 접속 후 jupyter notebook 실행
~~~
$ jupyter notebook
~~~

현재 사용되는 인식 엔진에 대해
------------------------

* 현재 사용되는 인식 엔진은
  * 얼굴 검출은 정면으로 제한된다.
  * 한 사람에 대한 결과만 return 한다.
    * 얼굴이 2개 이상일 경우, 결과 return의 기준은 얼굴의 크기로 정의된다.
* 학기 프로젝트를 위해 사용이 필요한 경우 junhee.heu_at_sk.com 으로 연락 요망

* 관련 사용법은 [사용설명서](https://drive.google.com/open?id=1xdimVwZrJDpLWi5YQWzTPKJZ-1Cbf0fcQdnPoTLYbNc) 를 참고한다.
* Gallery 등록을 위해 ([postman_collection파일_Download_Link_1](https://drive.google.com/open?id=1vHNmktm4SE9MIIBXWY1s9qh6eGJjVNxY) or [postman_collection파일_Download_Link_2](https://github.com/junheeheu/skt_ai_lecture_2018/blob/master/VIC%20API.postman_collection.json))을 다운받아 사용한다.

* [git-link](https://github.com/junheeheu/skt_ai_lecture_2018)

* [관련-추가-정보들](https://tde.sktelecom.com/wiki/pages/viewpage.action?pageId=180979799)
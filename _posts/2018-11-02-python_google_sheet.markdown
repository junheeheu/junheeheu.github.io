---
layout: post
title:  "Python & Google Sheets 연동 - 읽기 가능 예제"
date:   2018-11-02
categories: [python]
tags: [2018, python, google_sheets]
---

파이썬을 이용한 구글 스프레드 시트 사용 - 읽기 가능 예제
================================
근데 이건 읽기만 가능한 것 같은데....


구글 credentials.json 받기
--------------------------------
* [구글 개발자 사이트](https://developers.google.com/sheets/api/quickstart/python?authuser=1)에 접속해서 "ENABLE THE GOOGLE SHEETS API"를 클릭
  * 아래 붉은 색 박스를 클릭
  * 다운로드 configuration file
![step1](https://lh3.googleusercontent.com/b2WoYO-LIOgw-XPww-GWATc2pwwlmIQaoI1PYlbVvgHUiKnoZGEFpFXytXgwvoAE6oiKPlJGNoYhXgw4YU46kg08Bb9rUtKQ9WWGf2wLDbprlvRfAUNo7x-mpKQq5n-RYA5Oq3yI22qGoA_NRyubk3N1MuPMvaa0Lp55IYyucbQ2Mfzmm7wI9Agx4kVoj5BkC_rzQGdCMaPOKvuq2_epztZKFsfWrmi3nfB4V9Nq1yIXs3ifJOG7Rj0CC9ON0qRXbPSwABZz62AQOt8LCIWX2IkJyIx--knwe5aSnCGel_8OiVJ4k8anQJ1wvBm8wgIR9i_wJUBkN-N_ps87ss26tfZPRyavD0jHdkNKrS4xVAriwM5_tAnakuvvE9fm4-KpLPzgaaEelslY_Azn-wT2JWCS-vSfofvvlp8kr3kM7GYgxNhae0Y9NVQqwBRbl2nrKX2RP2PjO9Skgfb2np5v8ytRnuZcHpeExxXFyECO2ZGKJdgEDPqajvZenJDn9W3m8zvBLBELfLPF2EQBq3u-5K--kM6MBohHrYfcMBSvyTDnN-W28BNQ3OvGE4_moKirY8y0Km5nlr_U2tkfjXjfNeQ8xb2XtgDaNyNKVsluEqn3X9LVsbhhGUBot8ricgkvtyTsRFwOkVW-ixAyCRQBdCnraQ=w1618-h484-no)

Google Client python Lib. 설치
------------------------
~~~
pip install --upgrade google-api-python-client oauth2client
~~~

테스트 코드
----------------------
```
from __future__ import print_function
from googleapiclient.discovery import build
from httplib2 import Http
from oauth2client import file, client, tools
```
```
SCOPES = 'https://www.googleapis.com/auth/spreadsheets.readonly'
SAMPLE_SPREADSHEET_ID = '1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms'
SAMPLE_RANGE_NAME = 'Class Data!A2:E'
```
```
def main():
    """Shows basic usage of the Sheets API.
    Prints values from a sample spreadsheet.
    """
    store = file.Storage('token.json')
    creds = store.get()
    if not creds or creds.invalid:
        flow = client.flow_from_clientsecrets('credentials.json', SCOPES)
        creds = tools.run_flow(flow, store)
    service = build('sheets', 'v4', http=creds.authorize(Http()))
    SPREADSHEET_ID = '1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms'
    RANGE_NAME = 'Class Data!A2:E'
    result = service.spreadsheets().values().get(spreadsheetId=SPREADSHEET_ID,
                                                range=RANGE_NAME).execute()
    values = result.get('values', [])
    if not values:
        print('No data found.')
    else:
        print('Name, Major:')
        for row in values:
            # Print columns A and E, which correspond to indices 0 and 4.
            print('%s, %s' % (row[0], row[4]))
if __name__ == '__main__':
    main()
```
* SAMPLE_SPREADSHEET_ID 는
  ![step2](https://lh3.googleusercontent.com/xb_ocy6Rfntvb4wnLUscO2bEOY5CiW3B-8NAcCdQHjaVHcj3EOh2DVAxYs0Lr2iO7-L1l6mMQ0ibDzKvMiokiKsdtZ-gWl45nyuTHRIJDmiK4amWkevLHgfuOfGhJB-u3CV7AWr4qeme5hwck2lXRKo_-quXU0l-9pmMNvIu2KXSoFlhSJGPP_ERsoRLDVLFPfllAsqFZ7g11BVkUrakWr60ik-2b3wgPmNNPG9jmVuRWT53xniTbZPWVUbYmgbDr0DhDaSYHPJzTaLmz4KBkreROVvXgFtalbSp_UkFswAanaOYEmIGHFbY91qFP21khqISOkaojZ3xMtugG4X3LdytKHP4ZTggBLL9Yj9zmzbpypdcxeOcHM2pSusQosoJCgMSjudF1OVSY677mqFEDwUKaaZN9gV4LF3hh_bDffvUK2xG8VCVYszsW8SCs1SNse2uZZWdVaaQWddSVbYM_RQ0Si0Kw3l6j0NWgw270Kg1KMm3pTCPOXBmeeNLS7rIkexM6xcI223eU9E43N-BHvMN7Gsh6VX_yLVwnROFwoXLv3M67rSurOJriQWtrz01SOPQAJS4Xu7_cRf3i0VgBxeLzlt8ARHD4L2dJ0AM2QRcwhi17NfoKDEwxSqjNYyycuz9KHzsX8XrMn6nTpno7gK-gw=w1522-h140-no)
  ~~~
  SAMPLE_SPREADSHEET_ID = '1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms'
  ~~~
* Class Data!A2:E 의 Class Data는 탭의 이름
  ![step3](https://lh3.googleusercontent.com/tLf3StFBtE4lnSc7qWYj8279UgbwiKvS6lj_bGja3OQsEIQVEsFbllwl8wFLh9PB_OvfYVl3TwRB9eyU1ERNazo-PqNhCX29OI5E7PG_mndMqolD6wtbqmz4MpOAPl_d5YrKbDOyOaAXntLbc3q0Dnz73DayEiWJya3JUJ3Wqf4O5qUpenchH3CpeXZfESsy8a-NtVdrYB7AecY_oMn-soX856CopfEgG3pfZ2co6epp_4tiHYJ7V1RQ7kMD7AYNu-snhs78Xq_7UAOV4ZiaVAP_nDdJaplnOaCSWf_wjrYnGPYJhVkMJpzkJdKhDTX1z7tnU0hAQuRo3NlsdswMTgNrmBMULoulSTAl66HhjIMPbc_Zk74fsMM6i5Y8__sLxDYtnPSDcnkhv9p_UZnYIQXbUh2KwZ-mtziD2jnh2sb92dNOqvrBpemQblp-9yGAcrIJkln6nStlauqcmxrqKmlA2iVdOShJTD-IFkl3XxAzirRiFlIqgKAZrEzSxVQrr4AE-4zjiXiSNwzysa1H_2y5zdNITLQD2OXQwsJhaPq28XQbC8xx6fzOfkMnIfh_tizgaRspJ2-NiWVC7fWxD4uZ3SHXla0nXlkknKF5zn3-fRyQfhz20Js1mLAuqTZRhwbz5_GCQSv9DMUqfNVgaiFtOQ=w868-h338-no)
  ~~~
  RANGE_NAME = 'Class Data!A2:E'
  ~~~

허용 하기
---------------
* 위 코드를 처음 실행 시킨 후
  * 처음 실행 시키면 hold가 걸리며 무슨 link가 뜸..
  * 해당 링크를 복사해서 local pc의 웹 브라우저의 url에 넣으면 "허용" 을 하는 창이 뜸... 당근 허용하면 이제 부터 접근이 된다.
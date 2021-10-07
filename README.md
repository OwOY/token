## itsdangerous
- 加鹽 
```
import itsdangerous
salt='sdaf'#加鹽
t=itsdangerous.TimedJSONWebSignatureSerializer(salt,expires_in=600)#過期時間600秒

info = {'username':'baihe','user_id':1}
res=t.dumps(info)
token=res.decode()#指定編碼格式
print(token)
```
>> eyJleHAiOjE1NzUwMDczNjgsImlhdCI6MTU3NTAwNjc2OCwiYWxnIjoiSFM1MTIifQ.eyJ1c2VyX2lkIjoxLCJ1c2VybmFtZSI6InlhbmdmYW4ifQ.yUb3PW53V89ZX4Ci2qeaBJIiizt0JUAN_W9BBzg8QkIR1-uO7NQl6jizSUReOFGanWzfG19t7XFHCWv1JGMIZw

- 解密  
```
res = t.loads('eyJhbGciOiJIUzUxMiIsImV4cCI6MTU3NTAwNzM0MywiaWF0IjoxNTc1MDA2NzQzfQ.eyJ1c2VyX2lkIjoxLCJ1c2VybmFtZSI6InlhbmdmYW4ifQ.k-Q1VyN2TOlQ4flHHoiOYEMRaUEiN5Ms2JgeRdnCZWbQB-WwQ1FScoBWxFGkCYEPoWVpAjQxDBQeBesmulZupQ')
# res = t.loads(token)
print(res)
```
>> {'username': 'baihe', 'user_id': 1}

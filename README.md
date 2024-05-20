# openvpn

```
version: '3.8'

services:
  openvpn-as:
    image: openvpn/openvpn-as
    container_name: openvpn-as-new
    cap_add:
      - NET_ADMIN
    ports:
      - "943:943"
      - "1443:443"
      - "1194:1194/udp"
    volumes:
      - openvpn-data:/openvpn
    deploy:
      placement:
        constraints:
          - node.labels.worker1.data == true

volumes:
  openvpn-data:
```

* Default User is : `openvpn`
* To get the password check your log
* Brows the url : `https://localhost:1443/admin`

  ![image](https://github.com/excel-azmin/openvpn/assets/92359442/07b73314-222a-402a-9cf3-4a6799159294)

  

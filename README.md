#### :peach: javascript


## getCurrentPosition() 는 API로 사용자의 위치를 리턴합니다.

```html
<!DOCTYPE html>
<html>
<body>

<p>Click the button to get your coordinates.</p>

<button onclick="getLocation()">Try It</button>

<p id="demo"></p>

<script>
var x = document.getElementById("demo");

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(showPosition);
  } else { 
    x.innerHTML = "Geolocation is not supported by this browser.";
  }
}

function showPosition(position) {
  x.innerHTML = "Latitude: " + position.coords.latitude + 
  "<br>Longitude: " + position.coords.longitude;
}
</script>

</body>
</html>

```

getCurrentPosition() 를 지원하지 않는다면 유저에게 메시지를 내보냅니다. 성공하면 coordinates 오브젝트는 파라메터(showPosition)에 지정된 함수로 좌표를 리턴합니다.   
getCurrentPosition() 메서드는 성공하면 오브젝트를 리턴하는데 위도, 경도 및 정확한 속성들은 항상 리턴됩니다. 


#### 참고 영상 : https://www.youtube.com/watch?v=9sPNTMx7HfY

* https://en.wikipedia.org/wiki/W3C_Geolocation_API
W3C Geolocation API는 클라이언트 측 장치에 대한 지리적 위치 정보를 검색하기 위한 인터페이스를 표준화하기 위한 World Wide Web 컨소시엄의 노력입니다.
##### Location sources 중 발췌 
```
중략...
The Geolocation API does not provide the location information. The location information is obtained by a device (such as a smartphone, PC or modem), which is then served by the API to be brought in browser. Usually geolocation will try to determine a device's position using one of these several methods.

GPS (Global Positioning System)
This happens for any device which has GPS capabilities. A smartphone with GPS capabilities and set to high accuracy mode will be likely to obtain the location data from this. GPS calculate location information from the satellite signal. It has the highest accuracy; in most Android smartphones, the accuracy can be up to 10 metres.

Mobile Network Location
Mobile phone tracking is used if a cellphone or wireless modem is used without a GPS chip built in.

Wi-Fi Positioning System
If Wi-Fi is used indoors, a Wi-Fi positioning system is the likeliest source. Some Wi-Fi spots have location services capabilities.

IP Address Location
Location is detected based on the nearest public IP address on a device (which can be a computer, the router it is connected to, or the Internet Service Provider (ISP) the router uses). The location depends on the IP information available, but in many cases where the IP is hidden behind an ISP network address translation, the accuracy is only to the level of a city, region or even country.

```

#### Get current position
```
const watchId = navigator.geolocation.getCurrentPosition( position => {
  const { latitude, longitude} = position.coords;
  // show a map centered at latitude / longitude
});
```

#### Watch a position
```
const watchId = navigator.geolocation.watchPosition( position => {
  const { latitude, longitude} = position.coords;
  // 좌표를 이용하여 주소를 보여준다
});

```

#### Stop watching a position

Stop watching for position changes by calling the clearWatch() method



 이것을 이용하기 위해서는 php 또는 node 에서 제공하는 기능을 이용하여 데이터를 저장해야 한다


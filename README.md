#### :peach: javascript


## TTS 
> 오래전에 컴퓨터의 음향장치라는 것이 지금과 같지 않았을때 컴퓨터에서 오락을 할때면 짧은 사운드를 듣고 했다. 모뎀을 이용하여 인터넷을 할때 들곤 했던 연결음이 기억나기도 한다. 그러고보면 컴퓨터도 음성을 만들어 낼 수 있었다. 그러니 이런 것을 한컷 이용하여 TTS 로 발전한 것이리라 믿는다

Speech synthesis or text-to-speech(TTS) 는 컴퓨터 기반 creation artificial speech from normal language text이다.
일반 녹음된 음성과는 다르다. 이것은 컴퓨터에서 생성해낸 음성형태이다.


(줄임말로는 TTS, 한국어로는 '음성합성(音聲合成)'이라 부른다. 보통 TTS라고 하면 이것을 의미한다. 컴퓨터의 프로그램을 통해 사람의 목소리를 구현해내는 것으로, 성우 없이도 거의 모든 단어와 문장의 음성을 쉽게 구할 수 있다 )

## SpeechSynthesis
Web speech API 의 하나로 주어진 텍스트를 소리로 바꾸어주는 TTS API 이다.  
speechSynthesis는 speak, cancel, pause, resume 함수를 갖고 있어서 재생할 음성을 추가하거나 취소, 일시정지가 가능한다
여기서 speak() 함수는 SpeechSynthesisUtterance 를 인자로 받아야 한다. 

### SpeechSynthesisUtterance의 6개의 속성과 함수
 - text : 읽어야 하는 문구이다. 
 - lang : 따로 지정하지 않는다면 html 문서에 지정된 language를 기본값으로 취한다
 - voice  : SpeechSynthesisVoice 객체를 값으로 설정할 수 있지만 따로 지정하지 않으면 defaultvoice를 사용한다
 - volume : 최소 0에서 최대 1의 값을 갖고 있으면 기본값은 1이다
 - rate  : 말하는 속도로, 0 ~10 사이를 지정할 수 있으며, 기본값은 1이다.
 - pitch : 소리의 높이를 결정하는 것으노 기본값은 1이고 0~2 사이의 값을 지정할 수 있다
 - getVoice() 함수는 speechSynthesis 가 사용할 수 있는 SpeechSynthesisVoice 목록을 반환하지만 voice 목록이 초기화되고 voiceschanged 이벤트가 호출된 후에 getVoice() 이벤트가 사용할 voice 목록이 리턴된다

``` html
 <button onclick="say()"> click</button>
    <script>
      function say(){
       const mySpeech = window.speechSynthesis;

       const contents  =  new SpeechSynthesisUtterance('안녕하세요 지원자 홍길동입니다 ' );
       contents.voice = speechSynthesis.getVoices()[0];
       contents.lang="ko"
       contents.rate = 1;
       mySpeech.speak(contents)
      }

    </script>
```   

# W02_Color

__1.	RGB와 CMYK__     
* RGB: 가산혼합, 디지털에 사용
* CMYK: 감산혼합, 출력에 사용 <br/>
CMY만으로는 온전한 블랙을 만들지 못하기 때문에 K가 추가됨

사람이 볼 수 있는 색상영역>RGB>CMYK  <br/>  <br/>
![cmyk-rgb-color-gamut-300x269-1](https://user-images.githubusercontent.com/90597915/134773094-002281af-78cc-4f1e-948b-0cc97fb876ee.png)
 <br/> https://blog.pack.ly/en/graphic-design-in-a-nutshell-part-3-rgb-or-cmyk-which-and-when/cmyk-rgb-color-gamut-300x269/  
 <br/>   
 <br/>  
 __2.	Bit Depth__  
* Bit: 1픽셀당 표현할 수 있는 색상의 개수  
영상화질에 결정적인 영향  
ex. 8Bit: 2의 8제곱  
3Channel 8bit  
Red Green Blue  
256 x 256 x 256   
https://www.youtube.com/watch?v=1_mbGO_KNzg

* JPG: 8비트 쓰는 대표적인 포맷 (압축)
* RAW:10/12/16비트 (무압축)  
해상도 같아도 품질에 차이
<br/>
<br/>

__3.	Alpha__
<br/>
<br/>
투명도를 표현하기 위해 고안 
        
* 흰색 불투명 / 검정 투명 <br/>  
* full-color pixel은 알파를 포함한 RGBA <br/>
* ex. 포토샵 R채널: 흰색(255)에 가까울수록 빨강, 검은색(0)에 가까울수록 빨갛지않음
<br/>
<br/>

__4. Color Space__
<br/>

* Vector값  
  * Vector3_(x,y,z)축을 (r,g,b)로 표현   
ex. (255, 0, 0) 간단히 하면 (1,0,0)으로도 가능
  * Vector4(x,y,z,w) = (r,g,b,a)  
* Scalar값 = (x) : 방향없이 하나의 수치로만 표시
  * Integer 정수 0,1,2,3 ...
  * Floating point: 소수점 0.1, 2.35 …
* String 데이터 : a, abc, 2D, compositing ... (문자)
* Boolean: 0/1(off/on)  
<br/>

* Color Gamut (색영역)  
  
![rgb](https://user-images.githubusercontent.com/90597915/134778581-a10d0f19-7ae5-4714-85a8-aa4baf1181a0.jpg) ![color-gamut-5](https://user-images.githubusercontent.com/90597915/134778889-4e64c2cb-4abd-4e12-87a9-6a4222cf9d38.jpg)
http://learn.colorotate.org/color-models/#.YU7hVLgzaUk   
https://www.benq.com/en-me/knowledge-center/knowledge/color-gamut-monitor.html
<br/>
<br/>

같은 Bit여도 기기마다 큰 차이  
따라서 최종 상영 매체에 따라 컬러 조정 필요  
*표준은 ACES를 사용 <br/>

![Gamuts](https://user-images.githubusercontent.com/90597915/134778971-9882445f-d822-48af-be49-d46ebea8ebd9.jpg)
https://cgrenderdna.blogspot.com/2019/06/updated-acescg-workflow.html



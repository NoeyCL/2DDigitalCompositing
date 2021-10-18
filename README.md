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
<br/>
<br/>
<br/>
# W03_Gamma   
   
__1. Gamma__    
* Gamma: 화면의 밝기를 나타내는 곡선     
디스플레이마다 표현할 수 있는 능력이 다름     
기기에 따라 실제 이미지가 갖는 밝기를 제대로 표현하지 못함     
     
     jpg로 저장하면 감마가 인코딩 된 상태로 저장     
     감마 2.2가 규격이었기 때문에 jpg나 png 등 srgb포맷은 곡선을 지님    
 
* Gamma Encoding(감마부호화)의 목적     
     * 주어진 대역폭 혹은 정보양 내에서 최대한의 '화질'을 보여주기 위해서      
     * 역사적으로 CRT디스플레이(브라운관)에서 전송하는 데이터는 선형이기 때문에 최종이미지의 중간톤이 어두워졌다.     
          이를 원하는 밝기로 보내기 위해 역으로 밝게 해주는 과정     
          >CRT 디스플레이의 지수 응답 곡선은 대략 y = x 2.2 였으므로 방송국에서 이를 지수 1/2.2로 전송 신호(x)를 인코딩하여     
           보정하기로 결정     
          따라서 감마 2.2가 규격이 됨
     * 인간의 시각이 밝기에 대해 비선형적으로 반응하기 때문에 최적의 화질을 보여주기 위해선 비선형적으로 데이터를 인코딩하여 어두운 부분을 더 자세히 기록해야한다.          
     (*비선형적:비례하지 않고 변화 / *선형적: 직선적으로 비례하여 변화)                
     
        =인간은 시각적인 부분에서 밝은 구역보다 어두운 구역의 변화에 민감하기 때문에 어두운 구역의 정밀도를 높이기 위해 사용     
        ex. 어두운 부분의 25,26 차이는 매우 크게 느끼지만 밝은 부분의 200,201 차이는 크게 못느낌     
        > 선형으로 인코딩 하면 밝은 부분에서 시각이 지각할 수 없는 필요없는 데이터가 많아지고,     
          어두운 부분에서는 데이터가 부족해서 화질이 떨어짐=계단현상(banding현상) 발생     
         
        
          
     ![2105879620_FmMCnAa0_Gamma01](https://user-images.githubusercontent.com/90597915/137688701-0ee31c72-f39c-4fe3-86c4-02c63e3978a2.png)      
> -흰 선: 실제 밝기 강도, 녹색 선: 우리 눈이 받아들이는 밝기 강도     
-a처럼 리니어한(선형적인) 값에서는 밝은색이 더 많아 보이고 b는 동일하게 분포되어 있는 것 처럼 인식     
-따라서 a처럼 선형적인 값을 b와 같이 비선형인 값으로 보정

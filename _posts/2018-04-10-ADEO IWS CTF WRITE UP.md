---
published: true
---


ADEO IWS'18 Staj programı nedeniyle bir ctf düzenledi. Twitter'dan şu cümlelerle duyuruyu yaptıklarında _"4 Mart 2018 tarihlerinde düzenleyeceğimiz staj programımızı, 543'üncü doğum gününde ünlü sanatçı "Michelangelo di Lodovico Buonarroti Simoni"ye armağan ediyoruz." yarışma esnasında soruları, verilen bu bilgi ışığında çözmemiz gerektiğini anladık. Sorularla cebelleşirken bolca Michelangelo'nun hayatını okuduk, araştırdık, kültürlendik... 

Buradan ADEO ekibine teşekkür ederiz. 

## MİSC 300 


<img src="..\images\Misc300.png">
![Screenshot from 2018-04-01 11-18-34.png]({{site.baseurl}}/_images/Screenshot from 2018-04-01 11-18-34.png)



Görüldüğü üzere soruda bir misc.zip adında dosya verilmişti. İlk iş olarak .zip uzantılı dosyayı extract ettik. _canvas.png_ isminde bir QR Kod bulunan resme ulaştık. Genelde CTF'lerde verilen dosyalara yanılgıya düşmemek için file komutu ile göz gezdirmenizi öneririz. 




![Screenshot from 2018-04-01 22-19-11.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-19-11.png)



![canvas.png]({{site.baseurl}}/_posts/canvas.png)



![Screenshot from 2018-04-01 22-21-11.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-21-11.png)

Qr Kod bize şifrelenmiş bir metin verdi. Şifrelenmiş metni incelediğimiz zaman base64 olabileceğini düşünerek decode ettik, flag gelir bu sefer derken, karşımıza ascii kodlardan oluşan bir dizi geldi. 



![Screenshot from 2018-04-01 22-21-50.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-21-50.png)



Hemen Google Amca'da Ascii to Text araması yaparak, aşağıdaki şifreli metne ulaştık..

 ![Screenshot from 2018-04-01 22-23-09.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-23-09.png) 



VEEE... 



![sezar.jpg]({{site.baseurl}}/_posts/sezar.jpg)



R.I.P Sezar...


![Screenshot from 2018-04-01 22-24-56.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-24-56.jpg)

## REVERSE 300 

Soru da yine reverse.zip adında bir dosya geldi karşımıza, içerisine baktığımız zaman bir .exe uzantısıyla karşılaştık. 

![Screenshot from 2018-04-01 22-26-26.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-26-26.png)

![Screenshot from 2018-04-01 11-18-39.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-18-39.png)

Genellikle bu tip sorularda strings komutu ile (Linux altında) bir .exe uzantılı dosya kurcalanır, biz de aklımıza gelen ilk yöntemi denedik ve flag'e kolaylıkla ulaştık. 


![Screenshot from 2018-04-01 22-27-30.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-27-30.jpg)


## STEGO 200 

![Screenshot from 2018-04-01 11-18-43.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-18-43.png)


Soruda yine bir .zip uzantılı dosya verilmiş. Extract ettiğimiz zaman Michelangelo.jpg dosyası karşımıza geliyor. 


![Michelangelo.jpg]({{site.baseurl}}/_posts/Michelangelo.jpg)

Gelen resmi steghide extract -sf Michelangelo.jpg komutu ile extract etmeye çalıştığımız zaman bize bir parola girmemizi istiyor. Bu parolayı da deneyerek kolaylıkla bulabilirdik fakat şöyle bir tool yardımıyla da işimizi hallettik, parolanın kolay olmayacağı ihtimalini düşünerek. Resme strings yardımıyla baktığımız da yine herhangi bir elle tutulur bilgiye erişemedik. 

![Screenshot from 2018-04-01 22-39-32.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-39-32.jpg)



![Screenshot from 2018-04-01 22-39-57.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-39-57.jpg)


Şu bonusu da şuraya şöyle bırakalım... 


https://www.youtube.com/watch?v=3eTjWQMYWIQ.


## STEGO 400

![Screenshot from 2018-04-01 11-18-46.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-18-46.png)

Yine bir resim dosyası karşımıza geldi.. Önceki soruda kullandığımız adımları tekrarlıyoruz. 

![Screenshot from 2018-04-01 22-30-17.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-30-17.png)


![Screenshot from 2018-04-01 22-31-06.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-31-06.png)

Bu adımda da brute-force denedik. Fakat gerek ctf'in teması gerek dictionary açısından şansımız yaver gitmedi derken, description imdadımıza yetişti. 

Yukardaki görselde file komutu ile resmi incelediğimiz zaman description kısmında bir şifreli metinle karşılaştık, işimize yarayıp yaramayacağına bakmak için base64 ile decode ettik ve resmin parolasına ulaştık. 

![Screenshot from 2018-04-01 22-31-55.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-31-55.png)

![Screenshot from 2018-04-01 22-32-26.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-32-26.png)


![Screenshot from 2018-04-01 22-32-31.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-32-31.png)

![Screenshot from 2018-04-01 22-32-41.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 22-32-41.jpg) 

## WEB #1 {100} 

![Screenshot from 2018-04-01 11-05-11.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-05-11.png)


![Screenshot from 2018-04-01 11-06-25.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-06-25.png) 

## WEB #2 

![Screenshot from 2018-04-01 11-10-39.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-10-39.png) 

Soruda yine aynı ipucu verilmişti bizde yine ufak bir analize başladık. 

![Screenshot from 2018-04-01 11-10-25.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-10-25.png) 

Flag bariz bir şekilde ortadaydı. 

![Screenshot from 2018-04-01 11-12-21.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-12-21.png)

## WEB 4 - 200 

![Screenshot from 2018-04-01 11-09-44.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-09-44.png)

![Screenshot from 2018-04-01 11-09-11.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-09-11.png)



İlk önce verilen adresin sonuna /robots.txt yazarak nelere erişip erişemeyeceğimize bakmak istedik. Şu sahneyle karşılaştık. 


![Screenshot from 2018-04-01 11-09-22.jpg]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-09-22.jpg)

![Screenshot from 2018-04-01 11-09-31.png]({{site.baseurl}}/_posts/Screenshot from 2018-04-01 11-09-31.png)

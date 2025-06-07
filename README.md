# Yeltigin E2A-1 Sistemi
Yeltigin E2A-1 sistem kodları

                                  Yeni Güncelleme [v2.0.0]!  
->Eski adıyla Elbaren-29 adlı uçağımıza yeni anlamlı bir isim ve model belirledik  Yeltigin E2A-1.
v1.1.2 ve önceki sürümlerinde uçağı sürekli nRF24l01 Radio antenleri ve modülleri ile haberleştirmeye çalıştık ancak yaşanan bazı problemlerden dolayı bunu değiştirmek zorunda kaldık ve bu problemlerin başında antenlerin birbirleri ile bağlantı kuramamalarıydı. Topalm ~12 Saatlik bi araştırma ve denemelerin ardından modülün arızalı olduğunu tespit ettik ve haberleşmeyi farklı bi yol ile yapmaya karar verdik ve elimizdeki NodeMCU kartın esp8266 Wifi modülü olduğunu hatırladık ve haberleşmeyi internet üzerinden yapamaya karar verdik bu şekilde bağlantılarda kopma veya uçağı uçurmada belirli bi menzil ile sınırlandırmayacaktık , uçağın menzilini arttırmanın tek bi yöntemi vardı oda batarya kapistesini arttırmaktı yani batarya kapistesi ile  uçağın menzili birbirleri ile doğru orantılıdırlar.  

  MQTT ÜZERİNDEN HABERLEŞME  
-> Uçağı internet üzerinden haberleşmesinin daha mantıklı olacağına karar vermiştik ama şimdide bi sorunumuz vardı oda Server kiralamaktı. Uçağı her uçuracağımızda bi servera para vermek çok can sıkıcı oldurdu (daha çok para vermeye canım sıkılıyor :) neyse) o yüzden bazı arştırmalarımızın ardından MQTT serverları üzerinden haberleşebileceğimizi öğrendik amaç şuydu :  


        Kumandadan Gelen Veri ------> Bilgisayar Programı ------> MQTT Server ------> Uçak  
  
  
  Yukardaki şemada göserdiğimiz gibi önce kumadadaki Aruino Uno'dan joystic ve butonlardan gelecek olan veri bi bilgisayar programına aktarılacak burda önemli ve çok sıkıntılı bir problem vardı oda hem kumandadan gelecek olan veri hemde yazdığımız bilgisayar programı verileri serial yolu üzerinden alıp-okuyorlardı yani aynı portu kullanıyorlardı, bu şu anlama gelirki aynı port üzerinden birden fazla programda kullanmanız MÜMKÜN DEĞİL ama bazı programlar sayesinde sanal port açarak bu sorunu çözebilirdiniz ama... bu seferde bu programların tamamı ücretli çıktı yada sadece kısa bi süreliğine deniyebiliyordunuz tabii biz bu programın Crack'li yazılımızı bulduk (dosyalarımızdan indirebilirsiniz) ve bu problemi çözmüş olduk.Şimdide başka sorunlarımız vardı program serial port üzerinden verileri okuyabiliyordu ve servera bu verileri çok hızlı bi şekilde gönderebiliyorud (ortalama 50ms bi gecikme süresi var) ama uçağın bu verileri alması için internetin olması gerekiyordu ,bizde bu interneti hafif bi telefon kullanarak hem uçağı dengelemek hemde uçağın kartına internet vermek için kullanmaya karar verdik [söylemeden geçmiyim telefon ve SIM kartı bulmak zordu çünkü kimse özelliklede ilk uçuş denemesinde vermeye razı olmadı]  

Tabii sonrasında ve öncesinde onlarca belki yüzlerde problemimiz oldu ve hepsini çözdük son problemimiz ise bataryada oldu . Kabloların bataryaya sabit bi şekilde bağlamak için bir aparat tasarlarken bataryanın batarya olduğunu unutup iki vidayı birbirine temas ettirdik ve küçük bi patlamadan sonra bataryanın enerji vermediğin ama enerji aldığını anladık ve bunu tamir etmek için bu işlerden anlayan birine vermeye karar verdik ama bulamadık! bu yüzden kendimiz tamir etmek zorundaydık ,daha doğrusu benim tamir etmem gerekiyordu  

Eğer ki yanlış bi hamle yapıp hayatımı kaybettiysem ve canımı uçak için verdiysem , bu işlerden anlayan birileri ile bu uçağın semalarda uçurmayı asla unutmayın ama inşallah böyle bi senaryo yaşamayız ve bu uçağı son zamalarımız olsa dahi uçurabilmek hepimizin hayalidir...

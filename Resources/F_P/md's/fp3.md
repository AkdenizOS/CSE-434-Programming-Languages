Here is a detailed report and transcript of the video you provided.

# Video Analysis Report: Functional Programming with Scheme

## Overview
This video is a recording of an online academic lecture, likely a university course on Programming Languages. The instructor is presenting a chapter on "Functional Programming Languages," focusing heavily on the **Scheme** programming language, which is a dialect of Lisp. The lecture combines theoretical explanations using PowerPoint slides with practical, live coding demonstrations using a Scheme interpreter in a terminal window.

## Key Topics Covered

1.  **Introduction to Functional Programming:**
    *   Brief comparison with imperative programming.
    *   Emphasis on mathematical functions and the lack of state changes or mutable variables.

2.  **Lambda Expressions:**
    *   Explanation of anonymous functions.
    *   Syntax and usage of `lambda` to create functions on-the-fly.
    *   Examples showing how to define functions that return other functions (e.g., a `make-adder` function).

3.  **Special Forms: `define` and `let`:**
    *   Using `define` to bind names to values or functions (creating global variables or named functions).
    *   Using `let` to create local scopes and bind variables temporarily for calculations.

4.  **Higher-Order Functions:**
    *   **`map`**: Applying a function to every element in a list. The instructor briefly shows Python equivalents.
    *   **`reduce` (or fold/accumulate)**: Iteratively applying a function to elements of a list to combine them into a single accumulated value.

5.  **Function Composition and Application:**
    *   Discussing functional forms where functions can take other functions as parameters or return them.
    *   The `apply-to-all` concept.

6.  **Lisp Data Types and Structures:**
    *   Explanation of Lisp's primary data types: **Atoms** and **Lists**.
    *   Lists are represented as parenthesized collections.
    *   Explanation that Scheme is dynamically typed (originally "typeless").
    *   Under the hood, lists are stored as single-linked lists.

7.  **List Manipulation Functions:**
    *   **`CAR`**: Returns the first element (head) of a list.
    *   **`CDR`**: Returns the rest of the list (tail) after the first element.
    *   **`CONS`**: Constructs a new list by adding an element to the front of an existing list.
    *   **`LIST`**: A function to build a list from given parameters.

8.  **Control Flow and Predicates:**
    *   The `IF` statement: `(IF predicate then_exp else_exp)`.
    *   Predicate functions that return true (`#T`) or false (`#F`), such as `ZERO?`, `EVEN?`, `ODD?`.
    *   Equality predicates like `EQV?` and `EQ?`.

## Live Coding Demonstrations
Throughout the lecture, the instructor switches to a terminal interface running a Scheme REPL (Read-Eval-Print Loop) to demonstrate the concepts live.
*   He demonstrates creating simple anonymous functions using `lambda`.
*   He shows how to bind functions using `define` (e.g., creating a `square` function).
*   He attempts to demonstrate the `reduce` function but encounters syntax errors, highlighting the importance of correct parenthesis matching in Lisp-like languages.
*   He demonstrates the `IF` statement to create a function that checks if a year is a leap year (or similar logic).
*   He demonstrates the behavior of `CAR` and `CDR` on lists and dotted pairs.

## Q&A Session
At the end of the lecture (around 20:16), a student asks a question regarding "programming challenges" mentioned earlier in the course. The instructor clarifies that these will be small, short assignments given out over the next few weeks to test specific concepts, rather than large-scale projects. They are meant to be completed relatively quickly.

---

# Video Transcript

**00:00 - 00:35**
**Murat Ak:** İşte programming challenges var. Ee onları vereceğim dediğim gibi. Ee niyetim de 6 tane 6 tane falan vermek var, beşer puanlık. Ee mock cheat sheet bunu verdik zaten. Weekly quiz, bunları yapmaya devam edeceğiz ama bu hafta değil daha. Ee lex yacc de, yacc ödevi ee geçenlerde var, dün diye hatırlıyorum evet. Onu da zaten yayınladık tamam. Şimdi bunlar böyle.

**00:35 - 01:08**
**Murat Ak:** Ee bu hafta kaldığımız yerden devam. Şimdi bu functional programming'i devam edip ondan sonra da tekrar programlama dillerinin tasarım prensiplerine geri döneceğiz. Buradan devam ediyorum ben. Şimdi hatırlama olarak geçen, tabii iki üç hafta önce hatta midterm haftalarından önce bunlardan bahsediyorduk.

**01:08 - 01:47**
**Murat Ak:** Functional programming işte çeşitli diller, avantajları, dezavantajları ee vesaire. Lambda expression. Şöyle kısaca hatırlatma babında hızlı geçeyim. Lambda expression neydi? Ee bir fonksiyon yaratma şekli. Yani lambda calculus ee ifadelerinden ee fonksiyon yani anonim, anonim fonksiyon yaratıyoruz. Mesela burada `(lambda (x) (* x x x))` dediğimiz zaman, x çarpı x çarpı x dediğimiz zaman, bu aslında x küp fonksiyonunu burada on the fly bir şekilde yaratmış oluyoruz. X küp fonksiyonuna da 2'yi verdiğimizde 8 yanıtını alıyoruz. Yani bu şekilde lambda buydu.

**01:47 - 02:18**
**Murat Ak:** Lambda calculus. Burada işte birtakım lambda calculus işlemleri yaptık. Nasıl yaptığımızı falan gördük. Ondan sonra burada define çeşitli Lisp, daha doğrusu Scheme dilindeki bazı reserved word'ler, bazı yani fonksiyonlar, dilin kendisinde olan fonksiyonlardan bahsettik. Mesela `(define pi 3.14159)` dediğimizde pi'yi define etmiş oluyoruz. Bu yani artık pi'nin yerine bunu yazacak demek, replace edebiliriz demek geri kalan yerlerde.

**02:18 - 02:47**
**Murat Ak:** Lambda'dan bahsetmiştik zaten. Burada mesela ee make-adder. Mesela burada hani fonksiyon da yaratabiliyoruz define'la. Mesela define'da sadece böyle bir değişken değil, yani mesela bu şekilde nerede o? Define'da sadece böyle bir değişken değil, bir fonksiyon da yaratma şansımız var. Yani `(define (square x) (* x x))` dediğimizde mesela, bunu dediğimizde artık square x fonksiyonu bir kare alma fonksiyonu olmuş olarak tanımlanıyor böyle yaptığımızda. Veya işte ee...

**02:47 - 03:30**
**Murat Ak:** Sadece şey değil, yani sadece böyle square x yani x alıp da square'ini döndüren bir fonksiyon değil, aynı zamanda parametrik bir fonksiyon da yapılabilir. Yani şöyle diyelim. Mesela burada square x'in cevabı bir sayı olarak dönüyor. Biz bu fonksiyonun cevabının bir fonksiyon olarak da dönebilmesini istiyoruz. Yani mesela define'da bunu da yapabiliriz. Yani ee neticesi square'deki gibi bir sayı olan değil, neticesi fonksiyon olan fonksiyonlar da yaratabiliriz. Yani bu ne demek? `(define (make-adder num) ...)` Bu ne demek istiyor? make-adder num diye bir şey gördüğün zaman, bunu şu lambda ifadesiyle oluştur demek.

**03:30 - 04:21**
**Murat Ak:** Bu lambda ifadesi ne diyor? Bir tane x alırsa onu x + num yapsın diyor. Yani mesela diyelim ki num her neyse mesela, num mesela 4 ise, ee gelen sayıyı 4'le toplayan bir fonksiyon oluştur demek bu. Bu da ne demek oluyor işte `(make-adder 4)` dediğimiz zaman, burada bir 4'le toplayıcı, yani 4'le toplayıcı diye bir fonksiyon yaptık aslında biz burada. 4'le toplayan. Yani buna hangi parametreyi verirsek verelim artık 4'le toplayan bir fonksiyon oldu bu. Gördüğünüz gibi bu şey bir fonksiyon yani ee parametrik olarak fonksiyon üretebilen bir fonksiyon gibi oldu. Yani make-adder artık istediğimiz adder'ı oluşturabileceğimiz bir meta fonksiyon gibi yani ee oluyor. Dolayısıyla işte `(make-adder 3)` dediğimiz zaman 3'le toplayan, istediğimizi yapabiliyoruz yani.

**04:21 - 04:57**
**Murat Ak:** Ee bu şekilde yani functional programming'lerde ee en önemli avantajlardan bir tanesi yani ee fonksiyon üreten fonksiyonlar veya fonksiyonları daha rahat bir şekilde manipüle edebilme, fonksiyonlarla daha rahat oynayabilme. İşte fonksiyonların çıktısı ve girdisi olarak başka fonksiyonlar ee koyabilme veya elde edebilme özelliklerinin daha ee rahat bir şekilde olması. Bunlardan bahsetmiştik.

**04:57 - 05:46**
**Murat Ak:** Ondan sonra define işte mesela operate-twice. Burada iki tane lambda iç içe girmiş. Mesela burada işte operation one, operation two falan diye ee burada yani şu işlemi yapmaya çalışacağız aslında. Ee yapacağımız şey mesela operate-twice deyip de iki tane burada operator verdiğinde ve şu sayıları verdiğinde, burada şu fonksiyonun, yani şurada oluşan fonksiyonun tam olarak ne yapacağını burada tasarlamış oluyoruz. Yani burada ee ne demiş? Mesela şu yeşil parantezlerin içerisindeki oluşturduğu lambda x ve y aldıktan sonra önce operator 1'i x ve y üzerinde kullanan, daha sonra operator 2'yi de bunun çıktısıyla y üzerinde kullanan bir fonksiyon ee oluşturuyor.

**05:46 - 06:51**
**Murat Ak:** Bu oluşturduğu fonksiyon da ee yani bu yeşil kısım da ee şu lambda'nın oluşturduğu şey. Yani bu lambda operator 1 ve operator 2 alınca operator'ları alan lambda böyle bir fonksiyon oluşturmuş oluyor. Yani x ve y aldığında üzerine önce operator 1'i, sonra da operator 2'yi uygulayan bir fonksiyon oluşturuyor bu kırmızı parantez içindeki lambda. Ondan sonra da operate-twice da zaten evet bu fonksiyona eşitlenmiş oldu. operate-twice yani ne yapıyor? İki tane operator alıyor. Bu operator'ları da burada tanımlanan şekilde, sırayla ee tanımlanan parametreler üzerinde kullanıyor. Mesela böyle bir fonksiyon tanımladığımızda, bu şuna tekabül ediyor. Yani 2 ile 3'ü çarpan, ondan sonra da yani çarpan niye? operator 1. Birinci sıradaki operator'ı x ve y üzerinde kullanan. Yani 1. sıradaki operator'ı x ve y üzerinde kullanan. Daha sonra da oluşan şeyle, oluşan şeyi artı operatörüyle, y yani 3'le kullanan, ikinci şeyle kullanan, ikinci parametreyle kullanan ee bir fonksiyon. Bileşke fonksiyon oluşturmuş oldu aslında burada. Bu şekilde yapabiliyoruz.

**06:51 - 07:10**
**Murat Ak:** Ondan sonra geldik let'e. let ee let aslında şey demek. Yani mesela biz lambda ile ne yapıyorduk? Anonim fonksiyonlar oluşturuyorduk. let ee aslında şöyle diyelim. Mesela biz lambda ile diyelim ki ee bir kare alma fonksiyonu oluşturacağız.

**07:10 - 08:00**
**Murat Ak:** *(Instructor opens a terminal window)* Mesela diyeceğiz ki işte ee `(lambda` aslında bir parantez daha açayım. Mesela şöyle `((lambda (x) (* x x))` mesela. Şimdi ondan sonra bunu oluşturduk. Bu bir fonksiyon artık. Şurası bir fonksiyon oldu. Şimdi burada bir de bunu ben uygularsam mesela 4'e, değil mi? Ne olacak? Bir dakika. Ee neyi yanlış yaptım? Şurada fonksiyon oluşturdum. Ee... Bir dakika niye yanlış oldu?

**08:00 - 08:15**
**Student:** Hocam fazla parantez var.
**Murat Ak:** Efendim?
**Student:** Fazla parantez var hocam.
**Murat Ak:** Fazla parantez mi var?
**Student:** Ha yok yanlış görmüşüm.

**08:15 - 09:03**
**Murat Ak:** Parantezler doğru. Lambda'da mesela şimdi bakıyorum bir dakika. Ee lambda'da ne yapıyoruz? Ee... `(lambda (x)` x'i de parantezleyim buradaki yaptığı gibi. Veya 4'e ee şöyle yapalım. Ee bir dakika. Şöyle yapayım. `((lambda (x) (* x x))` Şimdi şu lambda'm bitti. Bu lambda üzerine de mesela 5'e kullanayım bunu. Evet hah şimdi oldu. x'i de parantezlememiz gerekiyormuş tamam.

**09:03 - 09:25**
**Murat Ak:** Ee mesela burada ne yaptık? Ee şu kısımda anonim bir fonksiyon oluşturduk. Yani şu highlight ettiğim kısımda anonim bir fonksiyon oluşturuyoruz. Yani x alıp da onun karesini döndüren bir fonksiyon oluşturuyoruz. Ondan sonra 5'e veriyoruz. let'te aslında bunu yapmanın kısa bir yolu yani let ee mesela bakalım şurada...

**09:25 - 10:28**
**Murat Ak:** Ne diyoruz? let'te ne yapıyor? Ee... Mesela biz istiyoruz ki define width 10, define height 5 dediğimizde calculate-area width height ee çağırdığımızda output'u 50 olarak versin istiyoruz. Ne demiş? define calculate-area width height. Yani biz burada mesela şu şekilde bir şey verdiğimizde, böyle bir yapı verdiğimizde bunun şunu anlayacak yani. calculate-area width height burada width diye bir parametre var, height diye bir parametre var. Bu ikisini çarpacak. Çarpacak ve area olarak döndürecek. Veya burada diyoruz ki `(let ((area (* width height)))`. Yani let area ee width çarpı height. Değil mi? Burası width çarpı height. Şunu parantezlemişiz. area mesela area 50 mesela burada geliyor. Area ee width ve height'ın çarpımı oldu.

**10:28 - 10:52**
**Murat Ak:** Daha sonra tabii display yapmak için burada area diye isimlendirmiş. Mesela bir saniye. Şurada ee bir saniye let. let'in daha güzel bir örneği de vardı şurada bir yerde ama neyse oraya gelmeden önce şunun bir basitini yapalım. Ee... Şuradan... Direkt let'le yapalım.

**10:52 - 11:54**
**Murat Ak:** *(Instructor is typing in the terminal)* Bir saniye. let let let... Ee let şöyle yapacağım bir saniye. Ee... Ee... Hah pardon. Bir dakika let x ee... Pardon let ee mesela `(let ((x (* x x)))` Ee... Bir dakika böyle olmaz yalnız, pardon. Mesela karıştırdım galiba.

**11:54 - 12:24**
**Murat Ak:** Ee bir saniye. Burada vardı ya let. Çok basit bir... şekilde... Yani şöyle aslında, lambda'nın ee lambda'nın şey versiyonu aslında, lambda'nın uygulanmış versiyonu diyebiliriz let için aslında. Bir saniye ben niye böyle... Şurada ee... Bir saniye. let'in...

**12:24 - 12:49**
**Murat Ak:** Area variable is not accessible outside the let expression. Yani burada area'yı bu yapıp ondan sonra da bunları yazıyor. let dedikten sonra ee yani on the fly olarak area'yı tanımlamış oluyor burada. Ondan sonra da area'yı yazdırıyor ve işi bitiyor yani bu şekilde yapan bir şey. Bir saniye. Mesela burada bunu kullanalım bir. Şunu alalım şuradan. Direkt bunu yapalım.

**12:49 - 13:48**
**Murat Ak:** *(Instructor copies code from slides to terminal)* Şu şekilde. calculate-area, mesela artık calculate-area'yı kullanabiliriz. Ee define width. Şunları tabii yapmamız lazım. Width'i oluşturduk, height'ı da oluşturduk. Veya buraya 5 10 da yazabiliriz ama direkt ondan sonra şunu da yazdığımızda `(calculate-area width height)` dediğimizde 50 olarak dönüyor. Unspecified return value. return de yapılması gerekiyor galiba ama neyse bu önemli değil. Ee... Burada yapılan şey şunları bir silersem aslında daha rahat olacak ama burayı görmeniz.

**13:48 - 14:48**
**Murat Ak:** Bir dakika. width tamam bunlar zaten gereksiz. Şöyle yapayım. Hıh. Burada yapılan şey şu mavi kısımdaki let ee area'yı oluşturuyor. Burada da ne var? 3 tane açılan 3 tane kapanan. Şu kısım area'nın tanımı. Yani aslında şurada içerideki ee kısım, şuradan ee şuraya kadar olan kısım. Ee çeşitli, evet burada çeşitli ee nasıl diyelim, let dedikten sonra birer birer ee şeyler verilmiş burada. Ee tanımlar verilmiş. Area bu olsun. display "The area is" yazılsın. Ondan sonra tekrar area yazılsın ve newline atılsın diye. Ee yani daha doğrusu burada `calculate-area width height`'ın ee neler yapması gerektiği buraya ee konmuş. Burada da bunu yazdığımızda bunlar yapılıyor.

**14:48 - 15:30**
**Murat Ak:** Ee şimdi geçelim. Şu map'e. Map map ne demiştik? map de hepsine uygulama fonksiyonuydu. Yani burada on the fly daha doğrusu evet anonim bir fonksiyon oluşturduk. Burada ondan sonra bir liste olarak bunu verdiğimizde hepsine tek tek oluşturuyordu. Bunu görmüştük zaten geçelim. Ee Python'da da benzer şekilde yapılabiliyor demiştik. Yani burada Python'da map diye bir fonksiyon vardı hatırlarsanız, biliyorsunuzdur zaten. Bir tane fonksiyon tanımladığımızda `square` diye bir fonksiyonumuz var diyelim, aynı şeyi burada da yapabiliyoruz. Yani fonksiyonun adını birinci parametre olarak veriyoruz map'e, numbers'ı da, yani listeyi de ikinci parametre olarak alıyoruz, veriyoruz. Hepsine uygulayıp cevabı veriyor. Tamam. Bu da bu şekildeydi.

**15:30 - 16:04**
**Murat Ak:** Ee reduce'da fold and accumulate ee olarak kısaltabileceğimiz bir fonksiyondu. It is a higher-order function that takes a function, an initial value (accumulator), and a list or sequence as arguments. Burada birer birer yani iteratif olarak ee uygulayıp ee bir sonrakine ekleye ekleye gitme şeklindeydi. function is applied to the elements of the list, combining them into a single accumulated value.

**16:04 - 17:11**
**Murat Ak:** Mesela burada da reduce, mesela burada ne yapmış? `(lambda (acc x) (+ acc x))`. Ne demiş, burada accumulate ettiğimiz değer aslında şey ee... accumulate x dediğimiz zaman bu şuna tekabül ediyor diyor. Artı accumulate x. Yani bu değerle x'i toplayacağım diyor. Ve bunu tekrar tekrar uyguladığı zaman ne oluyor? Mesela işte ee birle ikiyi topluyor, oluşan değerle üçü topluyor, o şekilde giderek ee altıyı elde etmiş oluyor yani. Ee tabii en başta sıfırla başlıyor. Burada fonksiyon oluşturduğu, yani aslında şöyle görün bu olayı. Mesela şimdi burayı anlamak için şöyle düşünmeliyiz. Burada bir fonksiyon oluştu. Bu fonksiyon ne diyor bize? Fonksiyon diyor ki: `acc x` diye bir şey gördüğüm zaman diyor, bir input aldığım zaman diyor `acc x` diye, ee x'i `acc`'ye ekleyeceğim diyor. Ee ve reduce fonksiyonu da şunu yapıyor: ee şu şu değerin üzerine bunları işlem yapa yapa ekleye ekleye gidiyor.

**17:11 - 17:44**
**Murat Ak:** Yani mesela diyelim ki burada ne `acc x` görecektik ya. Burada 0 var. `acc`'nin yerinde 0 var aslında. x'in yerine de bunlardan birincisi olacak. 1'i sıfırın üstüne ekleyecek. Ondan sonra 2'yi 1'in üstüne ekleyecek. Burada 1 oldu artık çünkü, 3 oldular. Sonra bu üçü de bu oluşan 3 değerin üstüne ekleyecek, 6 elde edecek. Ve sonucu ee 6 olarak yazacak yani. Burada reduce'da bunu yapıyordu.

**17:44 - 18:40**
**Murat Ak:** Python'da da benzer olarak var. `functools`'tan `reduce`'u ekleyince. numbers ne demiş 1 2 3 4 5, tamam. reduce dediğimiz zaman `lambda acc, x: acc + x`. Burada aynı şekilde fonksiyon oluşturuyor. Yani x bana `acc` ve `x` verildiğinde `acc + x` oluşturan bir fonksiyon tanımlıyor burada. Ee burası onun tanımlama yeri. Verdiği de numbers ve sıfır. Zaten gördüğünüz gibi şey bile hemen hemen aynı yani, bütün ee yazım bile aynı. `lambda acc x` işte `acc + x` aslında. Ondan sonra da 0'la 1 2 3 4, 1 2 3 yani. Bunlar da aynı şekilde verilmiş bunlar. Burada sadece sıra değişik. Yani numbers başta, sıfır sonda, accumulate edilecek değer sonda sadece. Ondan sonra bu da aynı şekilde veriyor yani toplam olarak. Ee çarpı derseniz de faktöriyel buluyorsunuz vesaire. Yani bu şekilde ee yapılabiliyordu.

**18:40 - 19:27**
**Murat Ak:** Functional form. "A higher-order function, or functional form, is one that either takes functions as parameters or yields a function as its result, or both." Yani ee fonksiyonlara normal variable gibi davranıldığı zaman ee bunlara higher-order function diyoruz. Yani bir fonksiyonu parametre olarak alıyor veya return ediyor. Function composition ee burada da yine bileşke fonksiyonları görüyoruz. Yani burada f o g ne oluyor? Önce g'yi uygulayan, ondan sonra da h'i uygulayan biliyorsunuz. Matematikte de olduğu gibi bileşke fonksiyon. Yani bunlar bildiğimiz şeyler zaten. Geçiyorum burayı.

**19:27 - 20:16**
**Murat Ak:** Apply-to-all. Yani burada lambda calculus'te alfaya tekabül ediyor bu. Bir tane fonksiyon var elimizde h diye, bunların hepsine uygulanacak. Buna alfa yazıyoruz lambda calculus'te. Bu `map` ile yapılan bir şey sonuçta, bu ee şeyde. Ee functional programming dillerinde map ile yapılan şey aslında. Apply to all olmuş oluyor zaten.

**20:16 - 21:00**
*(Instructor switches to terminal, there's a pause)*
**Student:** Hocam bir şey soracağım.
**Murat Ak:** Efendim?
**Student:** Bu dersle ilgili değil de şey bu programming challenges'la ilgili. Onları siz hafta hafta ödev olarak mı vereceksiniz?
**Murat Ak:** Hafta hafta ödev olarak. Bunlar şöyle düşünün gençler. Mesela diyelim ki ee 30-40 sayfalık bir ee kod, 30-40 sayfa diyorum ya, 30-40 satırlık bir kod yazacak şekilde, atıyorum ee çeşitli ödevler, farklı dillerden yani bu functional programming dilleri olabilir veya işte bazı scripting dilleri var, onlardan da biraz bahsetmek istiyorum ben aslında, awk gibi pearl gibi. Bazı diller var ee bahsedebileceğimiz. Yani farklı, daha doğrusu o konuşacağımız aslında şeyler var.

**21:00 - 22:38**
**Murat Ak:** Ee bazı dillerdeki işte dynamic scoping falan filan gibi bazı farklı fikirler var. O fikirleri demonstrate edici birtakım ödevler vermek istiyorum. Çok da zor olmayacak, onlar biraz açıkçası kolay puan alacak gibi görünüyor yani. Ee ama ee en azından biraz hani programlama yapalım, bir şey yapalım yani. Böyle ee projenin ee yanında ee yani demek istediğim şu aslında: Ee programlama dillerinin ee çeşitli dizayn prensiplerinden bahsedeceğiz ya sonuçta. Yani bunların ee nasıl olduğunu yani görmek gerekiyor. Onun için böyle bir eliniz değsin anlamında aslında bunlar. Yani bazıları tabii zorlukları değişebilir. Kimisi mesela 10 dakikada yapacağınız bir şey, kimisi belki bir öğleden sonrada yapacağınız bir şey olur ama yani ee daha öyle beş gün uğraştıracak bir şey de olmaz yani, öyle söyleyeyim.
**Student:** Anladım hocam.
**Murat Ak:** Çıktısı, yani mesela diyelim ki bir fonksiyon yazacaksınız. O fonksiyonu ben ee belli sayıda input'la ee şey yapacağım, test edeceğim. Ee hepsine doğru verirse mesela puan alacaksınız tarzında. Yani böyle şey gibi, leetcode gibi filan yani düşünülebilir, kendimizin yaptığımız yani.

**22:38 - 23:43**
**Student:** Testlerini vermeyeceksiniz önceden ama ee?
**Murat Ak:** Siz de yapabilirsiniz, kendi yani ben de verebilirim de yani, verip sonra kendim daha kapsamlı bir teste tabi tutabilirim. Yani şey gibi yani bir bakıma. Ee aslında şey gibi yani, siz kendiniz de evde istediğiniz testi verebilirsiniz. Sonuçta kodunuzu yazdıktan sonra böyle extreme case'ler, olmayacak garip input'lar falan hani böyle boş input, işte integer overflow verecek input, ne bileyim böyle çeşitli input'larla denemek gerekiyor leetcode'da yapıldığı gibi. Yani onları verebilirim de yani ben çok da önemli değil. Çünkü herkesin zaten rahatça kendi kendine yapabileceği bir şey zaten o yani. Ee hani belki şey olur, çok extreme case bazı durumların ee düşünülmesi düşünülmemesi gibi bir şey test eder miyiz, bilmiyorum ama yani o şekilde. Genel anlamda o şekilde düşünebilirsiniz yani.
**Student:** Anladım hocam. Teşekkürler. Bence harika olur. Sağ olun.
**Murat Ak:** Aynen aynen böyle yani böyle bir şeyler yapmaya çalışacağız yani aynen. Tamam. Stop recording diyeyim ben burada bu kısmı.

**23:43 - 25:00**
*(Instructor interacts with recording UI, short pause)*
**Student:** Şey son beş haftadayız ya ee şu an her hafta vereceksiniz galiba bir de final haftasında vereceksiniz. Böyle altı tane olacak.
**Murat Ak:** Hızlı hızlı veririm ya ama bunlar şöyle düşünün yani zaten artık yani ee kod yazmak artık çok challenge olmaktan da çıktı gibi görünüyor zaten bu ChatGPT'lerle falan, takdir edersiniz ki. Yani ee yani belki ee biraz denerim ben ChatGPT'nin yapamayacağı tarzda da sormaya çalışabilirim ama yani ee çok hızlı bir şekilde yapılabilecek muhtemelen yani bunlar. Yani her halükarda yani çünkü ee onu zaten engellememiz mümkün değil. Ee biz sınıfa da sokup yapamıyoruz. Yani dolayısıyla ee bir programming challenge olarak yani ama bir şey en azından o fikirleri demonstrate edici birtakım ödevler vermek istiyorum. Çok zor olmayacak onlar, biraz açıkçası kolay puan olacak gibi görünüyor yani. Ee ama ee en azından biraz hani programlama yapalım, bir şey yapalım yani. Böyle ee...

**25:00 - 25:46**
**Murat Ak:** Düşünülebilir. Lisp data types and structures. Burada data type'lar, data object... Bunlardan da konuşmuşuz. Buralara sanki gel... Evet sonlara doğru gelmiştik buralara. Data object types: originally only atoms and lists. Burada şimdi Lisp data tipleri, ee sadece atomlar veya listeler olabiliyor. List form: parenthesized collections of sublists and/or atoms. Yani mesela bu şekilde bir liste var, listenin içinde başka liste olabiliyor vesaire. Lisp önceleri typeless bir language'miş. Yani herhangi bir type'ı yokmuş. Ee... Stored internally as single-linked lists.

**25:46 - 26:50**
**Murat Ak:** Yani mesela bunda nasıl yapıldı, bu şekilde gösteriliyordu zaten. İşte head ee ve next şeklinde linked list. Bildiğimiz data structure dersinde gördüğünüz linked list şeklinde tutuluyor. Datası burada, next'i burada. İşte ee tabii listenin her bir elemanı kendisi de liste olabildiği için böyle pointer başka bir listeye gösterebiliyor yani vesaire. Yani burada mesela ABCD'yi bu şekilde ifade edebiliyor şu ABCD dediğimiz şey. Veya işte A, ondan sonra BC listesi, ondan sonra D, ondan sonra iç içe işte E ve FG gibi. Bu şekilde yapılabiliyor. Mesela burada A var, A'dan sonra BC diye bir liste geliyor, BC listesi şurası. Ondan sonra D geliyor. Ondan sonra da E ee yani tabii önce bir liste açıyoruz. Liste açmak için bir tane pointer çektik, yeni bir listeye geçtik. Bu yeni listenin birinci elemanı E. İkinci elemanı ise yine FG diye bir liste, onun için yeni bir listeye gittik. Bu şekilde tree mantığında yapılabiliyor yani veya işte iki boyutlu bir linked list mantığıyla düşünülebilir.

**26:50 - 27:36**
**Murat Ak:** Lisp interpretation. Lambda notation is used to specify functions and function definitions, function applications and data have the same form. Ee burada bir ufak nokta. Mesela ABC diye bir şey gördüğümüzde mesela Lisp'te veya Scheme'de, neyse artık hangi Lisp dialect'i olduğu fark etmez çok, is interpreted as data. It is a simple list of three atoms: A, B, and C. If it is interpreted as a function application, it means the function named A is applied to the two parameters B and C. Yani burada ya üçlü bir liste olarak görülebilir bu, veya A fonksiyonunun B ve C'ye apply edilmesi olarak görülebilir. Ee bunu zaten ayırt ediyoruz biz.

**27:36 - 28:27**
**Murat Ak:** Yani mesela burada bir fonksiyon ismi varsa, bunlar function application şeklinde düşünebiliyor. Veya işte burada bir tane biz quote koyarak, quote koyarak bunu function application olmaktan çıkartabiliyoruz. Mesela işte burada ee mesela ne diyelim? `(define square x (* x x))` diyelim mesela. Böyle bir diyelim ki şey tanımladık. Bu bizim square fonksiyonumuz. Mesela `(square 4)` dediğimizde bunu liste olarak algılamıyor. Fakat mesela quote deyip de `'(square 4)` dersen, ee bu `(square 4)` olarak yani düşünülmüş oluyor. Yani S, Q, U, A, R, E harflerinden ibaret bir metin ve yanında 4 diye bir integer olan bir list yani. Sonuçta bu şekilde düşünülebilmiş oluyor böyle quote koyduğumuzda.

**28:27 - 29:20**
**Murat Ak:** Ee mesela şöyle bir şey yaparsak, `(5 6 7)` dersek mesela, burada Scheme'in bu implementation'ı, yani burada kullanılan compiler ee yani o şekilde implement edilmiş burada Scheme. 5'i yani quote kullanmazsanız kesinlikle bu 5'i function gibi görme eğiliminde. Yani burada normal bir liste tanımlamak isterseniz normal `(list 4 5 6)` gibi ee tanımlamak gerekiyor. Ee yoksa bunu fonksiyon olarak anlıyor yani. Daha doğrusu buradaki bir fonksiyon değilse ben bunu liste olarak anlayayım, madem 5 diye fonksiyon yok demek ki bu bir listeymiş demiyor, orada hata veriyor yani burada kendisi. Ee burada tarihinden bahsetmiş, bunları geçelim konuşmuştuk, olmadıysak olmalıyız bunları.

**29:20 - 30:05**
**Murat Ak:** Scheme interpreter'ı read eval print loop şeklinde olan bir şey. Normal diğerlerinde de olduğu gibi Python'da falan, e zaten burada onu yapıyoruz yani sürekli gördüğünüz gibi. Ee Primitive function evaluation. No particular order, parameters are evaluated in no particular order. The values of parameters are substituted into the function body. Bu functional programming'de çok öyle sıra zaten söz konusu değil fazla. Yani burada parantezler iç içe gittiği için, zaten parantezle sıralar belli oluyor yani. Ee The value of the last expression in the body is the value of the function. En son ne oluşuyorsa dışarıda o olmuş oluyor.

**30:05 - 31:04**
**Murat Ak:** Primitive functions and lambda expressions. Ee bu böyle şeyler var. Bunları zaten tek tek bakmış olmalıyız biraz. Lambda var. Lambda'yı biliyoruz zaten. Lambda expression'lar. Ondan sonra can have any number of parameters. Mesela burada işte parabol fonksiyonu yapıyor yani. Parabol fonksiyonu ne yapıyor, işte `(+ (* a x x) (+ (* b x) c))` şeklinde bunu oluşturmuş oluyor. Yani böyle şeyler yapabiliyoruz. Artık mesela böyle a, b, c, x dediğimiz zaman, bir parabolün x noktasındaki değerini hesaplayabilmiş oluyoruz yani öyle düşünün. Ee define pi, bunlar zaten yukarıda da vardı bunlar. Bu herhalde ben orada kendim ayrıyetten slayt hazırlarken bunları silmemişim. Bunlar ee orijinal slaytları yani kitabın. Ee Output functions: `printf` gibi fonksiyonlarımız var, `display` gibi fonksiyonlarımız var.

**31:04 - 32:01**
**Murat Ak:** Bunlar şey, ha bunlardan bahsetmiştik. `EVEN?`, `ODD?`, `ZERO?` ve `NEGATIVE?` diye ee boolean fonksiyonlarımız var. Bir sayının even mı olduğu, olmadığı, odd olup olmayışı veya zero olup olmayışı, negative olup olmadığı gibi hazır fonksiyonlarımız var. True bu şekilde gösteriliyor, false bu şekilde gösteriliyor. Küçük büyük harf fark etmiyor. Eşit değildir'in şekli bu. Yani ünlem eşittir değil, bu şekilde oluyor burada da. Ee The NOT function inverts logic of a boolean expression vesaire. Burada bunlar var. Neyse bakalım. Control flow.

**32:01 - 33:35**
**Murat Ak:** `IF` şu şekilde yer alıyor Scheme dilinde: `(IF predicate then_exp else_exp)`. Yani bu şeydekine benziyor aslında Excel'de hiç yazdıysanız `if`'i, yani `if`'ten sonra hemen logical kontrolü yazıyorsunuz, true olduğu takdirdeki şeyi birinci sıraya, false olduğu takdirdeki şeyi ikinci sıraya yazıyorsunuz. Mesela burada da `(IF (not (= count 0))` yani count eşit değildir sıfırsa, eee cevabı yani bu bunun sonucu diyor, şu ifadenin sonucu eee sıfır olmadığı takdirde ne olsun? `(/ sum count)` olsun yani. Mesela burada `sum / count`. Mesela ne diyelim? `(define sum 5)` diyelim. `(define count 3)` diyelim mesela. Ondan sonra `(if (not (= count 0)) (/ sum count))` kapattık. Unbound variable =. Bir dakika niye olmadı? Eşittir.

**33:35 - 35:08**
*(Instructor tries to debug the 'not equal' condition in the terminal)*
**Murat Ak:** İlginç. Acaba başka mı diyeceğim ama değil tabii. Burada bir, bir dakika şunu restart edelim ya. Restart 1 diyelim. Tekrar bir yapalım. Unbound variable. Eşit değildir, acaba burada farklı bir implementation mı var bilmiyorum ama. Neyse, şunu deneyelim diyecektim ama. Mesela şöyle filan mı denesek acaba? Mesela `equal` diyelim. Hatta `equal?` diyelim. Buna da `not` diyelim mesela, şöyle diyelim. `not` diyelim. Deneyelim bakalım bir de böyle deneyelim. Eşittir diyelim o zaman buraya bir dakika. Değil mi yani, pardon. Hah şimdi oldu. `not =`. Evet bu demek ki şunda bir sıkıntı var, onu bu implementation demek ki bu şekilde yapmamışlar. Neyse böyle kalsın. Bunu da kaydetmiş olayım. Ee, burada ilginç 1.6 falan yapmasını bekliyordum ama. Yapmadı, 1.66 falan. Evet 5/3 olarak yazıyor demek ki yani. Neyse.

**35:08 - 36:39**
**Murat Ak:** Evet burada da şu var. Ee control flow'da başka bir ifade `COND`. Bu `COND` switch case'e benziyor gençler. Burada ne demiş, leap year olup olmadığını bulma, yani işte 2010 leap year mıdır, değil midir, artık yıl mıdır, değil midir mesela onu bulmaya yarayan bir fonksiyon oluşturuyoruz. `leap?` adında bir fonksiyon yapıyoruz burada yani. Bir tane parametre alıyor, `year` parametresini alıyor. Ne yapıyor? `COND` açıyor, yani switch case açıyor aslında switch case açmış oluyor burada. İlk baktığı şey şu, yani hatta şurayı şöyle tam highlight edeyim, şu highlight ettiğim kısımda ne diyor? `ZERO?` mudur `(MODULO year 400)`. Yani 400'e bölünebilen bir şey midir bu year? Yani yılı 400'e modulosunu aldığımda 0 mı geliyor? Evetse, TRUE. Yani 400'e bölünebilen bir yıl, mesela 2400 yılı leap year, tamam. Değil, eğer 400'e bölünen bir yıl değilse, mesela 2100 yılı. 2100 yılı için mesela ne oluyor, buraya geçiyoruz. `ZERO?` mudur `(MODULO year 100)`. Yani 100'e böldük, 2100'ü 100'e böldüğümüzde 0 evet, o zaman FALSE olacak. 2100 mesela leap year değil. Veyahut da işte 2016. Mesela 400'e de bölünmüyor, 100'e de bölünmüyor 2016 değil mi? Ne oluyor ama 4'e bölünüyor 2016, ee o zaman ne olacak? Bunu geçtik, yani zero mu değil, zero mu değil. ELSE, o durumda şunu döndürüyor yani şu değeri döndürüyor nereye kadar? Şu. ELSE diyor şu highlight ettiğim değeri döndürüyor.

**36:39 - 38:04**
**Murat Ak:** Bu ne? Bu yine bir boolean value, yine TRUE veya FALSE gibi bir boolean value olacak çünkü `ZERO?` fonksiyonunun cevabı dönecek. O da ne diyor? `(MODULO year 4)`. Yani 2016'ysa mesela, ee 0 olacağı için TRUE dönecek, değil mi? 2016 TRUE. Ama 2015 ee FALSE dönecek mesela. Deneyelim. Mesela şunu aldık, alalım şöyle. Koyalım şuraya. Bir dakika, kopyalayamadık mı? Hıh. `leap?` diye bir şey oluşturduk diyor yani. `(leap? 2400)` Buna TRUE diyecek tabii ki. Dediğimiz gibi. `(leap? 2100)` Ee FALSE demesi lazım. Çünkü ikinciye giriyor yani burada. `(leap? 2012)` mesela, 4'e bölündüğü için ee TRUE diyecek. 4'e bölünmeyen bir şey de `(leap? 2001)`'e de mesela, ee FALSE diyecek yine. Gibi.

**38:04 - 39:20**
**Murat Ak:** List functions. `QUOTE`, listeyi... aslında şu ifadenin daha geniş hali bu `(QUOTE (A B))`. Yani A B'yi liste halinde düşün demek. Evaluate etme demek, o şekilde düşün demek. Ee ve `CAR`, `CDR` ve `CONS` fonksiyonları var yani. Bunları konuşacağız. Şimdi yine, şu anda benim sesim geliyor mu gençler?
**Student:** Evet geliyor hocam.
**Murat Ak:** Görünüyor değil mi? Herhalde imlecimi hareket ettirdiğim görülüyordur.
**Student:** Görünüyor hocam, yenileniyor bir şeyler.
**Murat Ak:** Hakikaten ha, görünüyor, ilginç. Halbuki "Not Responding" yazıyor. "Not Responding" yazdığı da görünüyor sizde değil mi?
**Student:** Yok o gözükmüyor.
**Murat Ak:** Enteresan, ben gördüm ama şimdi gitti. Neyse, ara sıra "Not Responding" olmaya başladı bilgisayar. SSD'yi değiştirdim, ee farklı bir SSD'ye clone yaptım, acaba clone yaparken bir problem oldu bilmiyorum. İkide bir ee programlar şey, donuyor, freeze oluyor, "Not Responding" diyor, bir süre sonra kendine geliyor ilginç. Daha önce yaşayan varsa belki bir fikir alabilirim yani niye oluyor. Belki tekrar kurmam gerekecek. Neyse.

**39:20 - 40:26**
**Murat Ak:** Quote, dedik, listeye çeviren şey. Yani liste olarak interpret etmemizi zorlayan ifade. Ee şimdi `CAR`, `CDR` ve `CONS` fonksiyonları var, onlara bakacağız. Bunlar ee, geçen sefer buralara gelmemiştik galiba evet, şimdi daha yeni bir yerdeyiz şu anda. `CAR`, hatta burada bir, belki bir ara verilebilir mi, 10.12, daha 20 geçmemiş, biraz bahsedelim o zaman, 20 geçe verelim. List fonksiyonları, şimdi `CAR`, ee bu 'kıdır' diye okunuyor gençler enteresan. İngilizcede de yani Vikipedi'sine baksanız 'kıdır' falan diye bir şey yani, kıdır diye okuyun diye söylüyor. Biraz komik ama dediğim gibi o şekilde okunuyor. `CONS` da construction fonksiyonu. `CONS` aslında `CAR` ve `CDR`'ın tersi gibi düşünebileceğimiz bir fonksiyon. Yani `CAR` bir listenin birinci elemanını, `CDR` da birinci elemanı hariç diğerlerini yani kuyruk, kuyruğunu ifade eden şey. Aslına bakarsanız şunlar...

**40:26 - 41:51**
**Murat Ak:** Yani `CAR` aslında şunu ifade ediyor, ee oradaki, yani onun valuesu diye düşünebilirsiniz. Bu da `CDR` da next'ini ifade ediyor gibi düşünülebilir aslında. Ee yani mesela burada `CAR (A B C D)` listesini verdiğimiz zaman, `CAR` A döndürecek. `CDR` da `(B C D)` listesini döndürecek. Dolayısıyla gerçekten de `CAR` bunlardan bir tanesine, `CDR` da bir tanesine tekabül ediyor gibi düşünebiliriz. Ee, ne dedik, evet. Yani mesela burada çeşitli örnekler var. `CAR` ee bu listeyi verdiğimizde, bu liste ilk elemanı kendisi de bir liste olan, sonraki elemanları normal sayı olan veya variable olan bir liste. Bu listeyi `CAR` uyguladığınız zaman buraya, `(A B)` dönüyor, çünkü ilk elemanı bir liste yani. Bunu şöyle düşünebilirsiniz yani aslında. Burada ee yani şöyleydi. Değil mi? Hatta şu şekilde göstereyim ben bunu. `CAR CDR CAR CDR` şeklinde gidiyor ya, bu mesela burada şu yine bir `A`... şurası, bak şimdi yine "Not Responding" dedi. Bir 5 saniye yani kendine gelmiyor. Task Manager'da bir şey görünüyor mu? % CPU % 8'de daha yani ilginç.

**41:51 - 43:35**
**Murat Ak:** Blocking olan şey ne yani burada? Task Manager'da "Not Responding" diyor bir defa. Neyse. Allah allah ya. Çaresiz bekliyoruz, neyse. Yani burada ne diyecektim, çizemiyorum ama anlatarak söyleyeyim bari. AB, işte AB ee şurada AB'yi çizecektim. Burada da C ve D var zaten. Burada `CAR` dediğimiz zaman şu oku aldığımız için AB dönüyor tabii, yani burada çünkü yeni bir liste var burada takdir edersiniz ki. Dolayısıyla bu listeyi ee, evet kendine geldi bilgisayar. AB ee şu şekilde, burası A, burası B gibi düşünebiliriz aslında. Burası da C ve D gibi düşünebiliriz. Bu da aslında A ve B'yi parantezlediğimiz liste yani, öyle düşünün. Yani şu listenin tamamı aslında olmuş oluyor buradan point ederek bunu sağlamış oluyoruz. Dolayısıyla `CAR` dediğim gibi, `CAR` şurayı döndürüyor, yani `CAR` aslında şu, `CAR` şu, `CDR` da şu. Yani `CDR` verseydik de `(C D)` diye bir liste oluşturacaktı yani mesela hah zaten burada var aynısı. Aynı listeye `CDR` verdiğimiz zaman `(C D)` diye bir liste oluşturacaktı. Listeleyip yapıyor tabii yani, bunu parantezleyip veriyor tabii. Burayı olduğu gibi veriyor, ama bunu parantezleyip veriyor.

**43:35 - 44:30**
**Murat Ak:** Mesela burada bir liste vermezsek error veriyor burada. Ama bunu parantezlersek A verecek. Mesela bakalım. Ee mesela burada `(CAR A)` dediğimiz zaman buna hata veriyor. First argument of CAR... Ama burada mesela şöyle yaparsak eğer, A veriyor. Yani artık liste olmuş oluyor çünkü parantezlediğimiz için. Tek elemanlı bir liste gibi görmüş oluyor bunu. Ve normal ee şey veriyor yani. Bunun `CDR`'ı da bir error. Aynı şeyin `CDR`'ını verirseniz de bir error çünkü liste değil. Bunun `CDR`'ını verirseniz de returns boş küme. Yani mesela aynı şeye `CDR` verirseniz mesela burada `(CDR '(A))` derseniz, tek elemanlı bir liste verirseniz, tabii tek elemandan sonra hiçbir şey olmadığı için null bir liste döndürecek, yani null. Ee evet boş bir liste daha doğrusu, null demeyelim, boş bir liste. Boş küme gibi düşünebiliriz.

**44:30 - 46:01**
**Murat Ak:** `CONS` construction da şöyle çalışıyor. Yani `CONS` da aslında şöyle düşünün aslında, `CONS`'la oluşturan şey öyle ki siz buna `CAR` çağırsaydınız buradaki birinci verilen şeyi, `CDR` çağırsaydınız ikinci verilen şeyi döndüreceği şekilde gerisin geriye tam tersine construct eden şey. Yani çok bariz yani dediğim, değil mi, çok anlaşılabilecek bir şey. Yani `CONS`'la iki tane parametre veriyorsunuz. Bunları bitiştiriyor birbirine öyle ki ee oluşan şeyin `CAR`'ı bu, `CDR`'ı bu olmuş olması gerekiyor yani. Mantık bu. Mesela burada nasıl işte `CAR` A B döndürdü, `CDR` C D döndürdü. Eğer siz `(CONS '(A B) '(C D))` derseniz, direkt bunu oluşturur yani mesela, değil mi? Niye, çünkü oluşan şeyin `CAR`'ını aldığınız zaman şunu döndürmesi gerekiyor, `CDR`'ını aldığınız zaman şunu döndürmesi gerekiyor ki burada gördüğümüz gibi öyle zaten. Yani `CAR` ve `CDR`'ın tersi aslında. Yani `CONS` o demek, `CONS` da ee...

**46:01 - 46:40**
**Murat Ak:** Yani şimdi bu `CAR`, `CDR` ve `CONS` çok önemli fonksiyonlar. Niye derseniz? Ee functional programming dillerinde iteration olmadığı için, yani iteration ee yapılamadığı için for loop, while loop filan öyle loop yapmak mümkün olmadığı için, iteratif şeyler ee neyle yapılıyor? Recursion'la yapılıyor. Veya bir listede ilerleme işlemi mesela. Listede ilerlerken, mesela diyelim ki listenin her bir elemanının karesini alacaksınız atıyorum. Birinci elemanının karesini aldınız, ee recursive olarak `CDR`'ına aynı fonksiyonu çağırıyorsunuz.

**46:40 - 47:31**
**Murat Ak:** Böylece mesela diyelim ki birinci elemanın karesini aldı, yazdı, ondan sonra geri kalanınınkini yapmak için recursive call attınız, oradan işte ikinciden sonrakileri, yani ikinciden sonrakileri parametre olarak veriyorsunuz, yani `CDR`'ı veriyorsunuz parametre olarak. Artık ondan sonra gerisinin karesini yazmaya devam ediyor yani böyle böyle bitene kadar gidiyor. Yani bu şekilde bir mantığı var. Ee mesela burada tabii liste, mesela bunlar `CONS`'ta bu da liste bu da liste olarak veriyoruz ki böyle olsun tamam. Ee ilk ilk kısmı şey olabilir, mesela şöyle yapalım. Ee `(CONS` mesela buna `A`, ikinciye de `'(B C)` verelim mesela şu şekilde. Bu tabii ki `(A B C)` güzel güzel oluşturuyor.

**47:31 - 48:10**
**Murat Ak:** Çünkü gerçekten bu birincisi liste olmak zorunda değil tabii ki çünkü `CAR` zaten liste olmayabilir, normal value olabilir. Ama bunun tersini yaparsak mesela, `CONS`'ta değil mi mantıken de zaten düşünürseniz buna büyük küçük fark etmiyor, mesela `'(A B)` dedik, buraya `C` diyemezsiniz. Yani derseniz de dotted pair oluyor daha doğrusu bu. Dotted pair, yani buradan kastım şu, ee normal bir liste oluşturmamış oluyorsunuz bu dotted pair gibi bir şey. Tuple gibi düşünebilirsiniz.

**48:10 - 49:20**
**Murat Ak:** `CONS` mesela burada da liste verdiniz diyelim `'(A B)`, ondan sonra diyelim ki buna `'(C)` verdiniz mesela. Burada da yine dotted pair yaptı. `CONS` ee başka bir şey kalmadı galiba zaten. Evet burada ee yani normalde burada tabii ikinciye liste vermediğiniz zaman hata verebilirdi ama hata vermiyor, dotted pair oluşturuyor. Ee List is a function for building a list from any number of parameters. Mesela list de yani bu şekilde verdiğinizde, bu size bir şey döndürüyor. Ee neyse yazalım. `(LIST 'a 'b 'c)` falan dediğinizde, bu size `(a b c)` diye bir liste oluşturuyor. Ee güzel. Predicate function `EQ?`. `EQ` bu şeyde benziyor tabii bu object oriented dillerdeki gibi düşündüğümüz için, mesela burada A ve A value olarak düşündüğümüz için, bunlar A harfi A harfine tamam eşittir, güzel.

**49:20 - 50:00**
**Murat Ak:** Bu da A harfi B harfine eşit değildir gibi düşünebiliriz bunu veya value olarak da düşünebiliriz. Ee bir listeyle bir listeyi, pardon bir value ile bir listeyi karşılaştırdığımız zaman tamam FALSE veriyor. Şunlar da bazen garip hareket edebiliyor. Yani `(A B)` listesiyle `(A B)` listesi eşittir dediğiniz zaman TRUE da ee FALSE da dönebiliyor. Veya işte 3.4 ile 3 ve 0.4'ün toplamını karşılaştırdığınız zaman yine ee farklı bir şey yield edebiliyor.

**50:00 - 50:18**
**Murat Ak:** Bunu yapmaması için `EQV?` var. `EQV?` fonksiyonu, değersel karşılaştırma yaptığı için, referansa göre değil de değerine göre karşılaştırma yaptığı için, mesela 3'le 3'e tamam TRUE diyor. A ile 3'e FALSE diyor. İşte 3.4'le 3'ün ve 0.4'ün toplamına TRUE diyor bu defa. Yani FALSE deme şansı bunda yok.

**50:18 - 50:35**
**Murat Ak:** Ee `EQV?`'ta ee mesela 3.0'la 3'ü verdiğiniz zaman FALSE veriyor ama, çünkü float'larla integer'lar farklı olarak değerlendiriliyor. Demek ki type'ına bakıyor önce, type'ı farklıysa direkt type farklı diyor yani eşitleme şansı demek ki yok o durumda.

**50:35 - 51:17**
**Murat Ak:** Ee şimdi burada bir duralım. Bir ara verelim. Bir dakika. Bir on dakika şey 30 geçeye kadar bir ara verelim. Ee ondan sonra devam ederiz. Şimdi şuradan... Hocam bir şey soracağım. Efendim heh. Tamam hocam. Tamam mı? Durduruyorum. Şey son beş haftadayız ya şu an her hafta vereceksiniz galiba bir de final haftasında vereceksiniz böyle 6 tane olacak. Hızlı hızlı veririm ya ama bunlar şöyle düşünün yani zaten artık yani ee kod yazmak artık çok challenge olmaktan da çıktı gibi görünüyor zaten bu ChatGPT'lerle filan takdir edersiniz ki.

**51:17 - 52:21**
**Murat Ak:** Yani belki biraz denerim ben ChatGPT'nin yapamayacağı tarzda da sormaya çalışabilirim ama yani çok hızlı bir şekilde yapılabilecek muhtemelen yani bunlar. Her halükarda yani çünkü onu zaten engellememiz mümkün değil. Biz sınıfa da sokup yapamıyoruz. Yani dolayısıyla bir programming challenge olarak ama bir şey en azından o fikirleri demonstrate edici birtakım ödevler vermek istiyorum. Çok zor olmayacak onlar, biraz açıkçası kolay puan olacak gibi görünüyor yani. Ama en azından biraz hani programlama yapalım, bir şey yapalım yani. Böyle projenin yanında, yani demek istediğim şu aslında, programlama dillerinin çeşitli dizayn prensiplerinden bahsedeceğiz ya sonuçta, yani bunların nasıl olduğunu yani görmek gerekiyor, onun için böyle bir eliniz değsin anlamında aslında bunlar.

**52:21 - 53:13**
**Murat Ak:** Yani bazıları tabii zorlukları değişebilir. Kimisi mesela 10 dakikada yapacağınız bir şey, kimisi belki bir öğleden sonra da yapacağınız bir şey olur ama yani daha böyle beş gün uğraştıracak bir şey de olmaz yani öyle söyleyeyim. Anladım hocam teşekkürler bence harika olur sağ olun. Aynen aynen, yani böyle bir şeyler yapmaya çalışacağız yani aynen. Tamam stop recording diyeyim ben burada bu kısmı.
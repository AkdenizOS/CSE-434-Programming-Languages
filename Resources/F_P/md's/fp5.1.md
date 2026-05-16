Here is a detailed report and a full transcript of the provided video lecture.

# Video Analysis Report: Functional Programming Languages

## Overview
This video is a recording of a university-level lecture, likely conducted via Microsoft Teams, focusing on functional programming languages. The presenter uses a PowerPoint presentation alongside a terminal window to demonstrate code execution. The lecture covers advanced concepts in Scheme, briefly touches upon Common Lisp, and then introduces the ML (Meta Language) and Haskell programming languages. The presenter speaks in a mixture of English (primarily when reading slides and technical terms) and Turkish (for explanations and interacting with the class).

## Key Topics Covered

### 1. Scheme: Functional Composition and Code Building
*   **Composition:** The lecture begins by explaining how to compose functions in Scheme using the `compose` function. The presenter demonstrates how to chain functions like `car` and `cdr` to extract specific elements from nested lists.
*   **Shorthand Notation:** He explains the shorthand notations for composed list accessors, such as `cadr` (car of cdr) and `caddr` (car of cdr of cdr). A significant portion of time is spent interactively working through a complex example: `(caaddr '(4 5 (6 7) 8 9))`, explaining step-by-step how the nested lists are evaluated.
*   **Apply-to-All (`map`):** A brief review of the `map` function, which applies a given function to all elements of a list.
*   **Functions that Build Code (`eval`):** The presenter introduces the `eval` function, which allows Scheme programs to construct and execute new Scheme code at runtime. He demonstrates an `adder` function that dynamically builds a list starting with the `+` operator and then evaluates it to calculate the sum.

### 2. Common Lisp
*   The presenter provides a very brief overview of Common Lisp, describing it as an older, larger, and more complex language compared to Scheme. He lists features like records, arrays, complex numbers, and macros, but does not delve into coding examples.

### 3. ML (Meta Language)
*   **Characteristics:** ML is introduced as a statically-scoped, strongly-typed functional language with syntax resembling Pascal. A key feature highlighted is its type inferencing system, which determines variable types without explicit declarations.
*   **Syntax and Structure:** The presenter shows basic function definitions (`fun cube x = x * x * x`), if-then-else selection structures, and pattern matching (e.g., defining a factorial function using separate cases for `0`, `1`, and `n`).
*   **Imperative Features:** While ML is functional, it supports imperative features. The presenter attempts to demonstrate a `while` loop using mutable references (`ref`), though he struggles with the specific syntax live during the lecture before moving on.
*   **Lists and Higher-Order Functions:** The lecture covers ML list syntax (using brackets `[]`), head (`hd`), and tail (`tl`) functions. It also demonstrates higher-order functions like `filter` and `map` with lambda expressions (anonymous functions defined using `fn`).
*   **Currying:** The concept of currying is explained, where a function that takes multiple parameters is transformed into a sequence of functions, each taking a single parameter.

### 4. Haskell
*   The lecture concludes with a brief introduction to Haskell, noting its similarities to ML but emphasizing its purely functional nature—meaning it lacks variables, assignment statements, and side effects. The presenter shows factorial and Fibonacci sequence implementations using Haskell's pattern-matching syntax.

---

## Full Transcript

**00:00 - 06:20 (Introduction and Scheme Composition - English)**
At the end of the lecture... so let's continue from here. Functional forms... we talked about it a little bit but it's about composite functions. When you have f and g, when you apply g first and then f, it is f o g, or g o f I think. You can define it like this. So you define `gx` as `3 * x` and `fx` as `2 + x` and then you can define a composite function. And in Scheme, the functional composition function `compose` can be written. So for example, you can write a function whose name is `compose` and it takes two functions. So here you can see all the parameters and the output, all of them are functions. So everything is a function here. This is a function, this is a function, this is a function. And the result that is returned here, it's also a function. So you can see that everything can be a function. 

So how do we do that? So we say `lambda (x) (f (g x))`. So this is the definition of the composite function that's going to be returned. And when you write this line, it produces a function `compose` which takes two parameters, two functions, and returns the composition of them. And then you can say `(compose car cdr)` for example, and then you can obtain a function which is an anonymous function here, it has no name, and then it finds the `car` of `cdr` of this. Which means here as you see, first g will be applied, so `cdr` will be applied and `(c d)` will be returned as a result of `cdr`. And then you apply `car` and you obtain `c`, right? So that's why this returns `c`. 

And then for example, you can say define `third_a_list`. For example, let's say you have a list `(a b c d e)`, you want to return the third one from the beginning. You want to create a function that returns the third element in a list for example. Then what you can do is you can write a function... you can form a function by using `compose`. You can say `(compose car (compose cdr cdr))` which works as follows: it first takes a `cdr`, and then it takes another `cdr`, and then it takes `car` of the resulting list. So you can form a function like this and then you can use it. For example, you can use this with a parameter for example let's say `(a b c d)`, right? Like this. And then this will return `c` for example. 

Anyway, but there is a shorthand of `car cdr` compositions. So `car` and `cdr` starts with c and ends with r as you know. So you can do this with `caddr`. It means you are going to compose a `car` and two `cdr`s, okay? So that's how you can write it. For example if you say for example `caddr`, it means you are first going to take a `car`, and then a `cdr` and then another `car`. Or if you can say `cdddr` for example, right? So you are going to take three `cdr`s. 

Let's run this. So this is Python. Let's say Scheme. And then we can say for example let's say `cadr` for example, and then `'(1 2 3 4)`. So as a result, what's going to be returned here? It's going to be `2`. Because we take one `cdr` which returns `(2 3 4)` and we take a `car`... I mean you are going to start from the end which is a `cdr` and then you are going to make a `car`. 

Or maybe you can say `(cadddr '(4 5 (6 7) 8 9))` for example. Let's... let me ask you, this will be a complicated one. Let's say... let's say... so close, close, close. Okay. Let's think about this, what will be returned here? Waiting for the answers. Any guesses? Maybe I can write all the options and you can like the correct option. `4`, `5`, `6`, `7`, `8`, `9`. Or maybe I don't know, maybe `(6 7)`. Right? That can also be returned. Or maybe `(6 7 8 9)` can also be returned. These are the options. What will be returned as a result of this call? 

**06:21 - 10:48 (Interactive Problem Solving - Turkish)**
Hiç tahmin eden de mi yok gençler? Ne dedik? Sondan başa doğru... yani `cdr cdr car car` şeklinde gidecek. Herhalde hiç şey yok, cevap gelmedi. Ben göremiyorum. Hah, bir tane `6 7`... nihayet bir cevabımız geldi. Düşünelim. 

Mesela burada `cdr`... ilk hareketimiz `cdr` olacak. `cdr` ne yapacak? Şu kısmı döndürecek değil mi? `(5 (6 7) 8 9)` kısmını döndürecek. Sonra bir tane daha `cdr` alacağız. Ne olacak? Şurası dönecek değil mi? Tam olarak şu kısım dönecek yani. Aç parantez aç parantez `6 7` kapat `8 9` kapat kapat kısmı dönecek. Sonra bir tane `car` alacağız. `car` aldığımızda `(6 7)` dönecek. Bir tane daha `car` alacağız... Bir adım daha gitmek lazım yani, o da `6`... 

Aa bir dakika `(6 7)`. Ben de şaşırdım burada. Bir dakika niye öyle oldu? `6` dönmesi lazım gibi geldi bana ama. `cdr`, `cdr`... Mesela deneyelim bir saniye, çok zor değil. Mesela şöyle yapalım. Mesela bir tanesini yazmasaydım ben bunun ne olacaktı? `(caddr '(4 5 (6 7) 8 9))`... Mesela bu şekilde yazsaydım ne olacaktı? Bir tanesini eksik yapsaydım. Bu olacaktı tamam. Peki ya `cddr` yazsaydım ne olacaktı? `(cddr '(4 5 (6 7) 8 9))`... 

Hım, liste içinde liste gibi dönmüş. Evet yani liste... yani bunun `car`'ını alınca yine kendisi kalmış oluyor. Yani niye peki liste içinde liste olmasın diye nasıl yazmalıydık? Hıh, evet tamam o zaman benim aslında sormaya çalıştığım soru şu mu oluyor yani? `caaddr`... o zaman şöyle demeliydim ben: `(caaddr '(4 5 6 7 8 9))` demeliydim. Doğru, liste yani evet liste olması lazım. Yani... eee zaten `cdr` zaten kendisi listeleştirip döndürdüğü için ben herhalde orada şaşırdım. 

Şimdi böyle dediğimizde `cdr` olacak şurası, şu kısım yani tam olarak şu kısım parantezlenip dönecek. Bir daha `cdr` dediğim zaman şu kısım parantezlenip dönecek. Şu kısım. Sonra `car` dediğim zaman bu defa `(6 7)` dönecek gerçekten biraz önce benim düşündüğüm gibi. Bir daha `car` dediğim zaman burası dönecek. Yani aslında `cdr`'ın parantezleyip döndürdüğünü unuttuk orada bir... Ben burada düşündüğümde şey oldu yani şurada şu dönecek olan kısmı bir daha parantezlediği için... evet doğru. Evet neyse `(6 7)` doğruymuş bravo. 

Evet şimdi bu şekilde olsaydı benim düşündüğüm gibi olacaktı. Doğru. `cdr`'ın parantezlemesi... Tamam. Evet neyse, burada dolayısıyla eee `car` ve `cdr`'ların daha hızlı bir şekilde composition'ının yapılabildiğini görüyoruz bu a ve d'leri ayarlayarak. İşte... buraya içeriye istediğiniz gibi a-d kombinasyonları koyabiliyorsunuz. O şekilde sağdan sola doğru yaparak geliyor yani composition şeklinde.

**10:48 - 14:50 (Map and Eval Functions - English & Turkish)**
Evet. `Apply to All`. Bundan zaten bahsetmiştik map-reduce kısımlarında. `map` burada da var. Burada `map` diyorsunuz, `lambda num` diyorsunuz, bundan zaten konuştuk. Yanlış hatırlamıyorsam burada anonymous bir function oluşturuyoruz, küp alan, küp alma fonksiyonu. Ondan sonra buraya da parametreyi verdiğimizde `map` zaten hepsine yansıtıyor bunu ve liste olarak döndürüyor. Bu nasıl listeyse bu da liste olarak dönüyor dedik.

`Functions That Build Code`. It is possible in Scheme to define a function that builds Scheme code and requests its interpretation. This is because we have `eval` function. This is possible because the interpreter is a user-available function `eval`. 

Bu demek istiyor ki, Scheme kodunu evaluate eden `eval` fonksiyonu, yani interpreter'ı, ekrana bir şeyler yazdıran şey, user'lara da açık olan `eval` olduğu için, biz bir Scheme kodu içerisinde kod yazıp onu tekrar Scheme interpreter'ına interpret ettirebiliriz diyor. Mesela burada bir örnek var. 

`Define adder_a_list`. Burada `eval`'ın kullanımı burada. `eval` burada büyük harf küçük harf fark etmiyor biliyorsunuz. `(define (adder a_list))`... Burada bir tane liste var. Sayı listesi olacak, adder yapacağız. Yani aslında burada yapmaya çalıştığımız şey şu: Öyle bir fonksiyon oluşturmaya çalışıyoruz ki adı `adder` olsun, ve buna biz bir sayı listesi verdiğimizde bunları toplasın. Bu şekilde bir fonksiyon yaratmaya çalışıyoruz. Yani artık `adder '(3 4 5)` dediğimizde bize 12 versin mesela. Bunu yapmaya çalışıyoruz. 

Diyor ki condition, `a_list` null ise 0 döndür. Yani listede bir şey yoksa zaten 0 dönsün. Else şöyle bir şey yapıyor: `construct` `+` `a_list` diye bir şey yapıyor. `cons` ne yapıyordu? Buradaki şeyleri listeleştiriyor. Yani burada aslında yaptığı şey şu: Şu şekilde bir şey oluşturuyor burada, `+` mesela `3 4 5` verdiyseniz siz, `(+ 3 4 5)` diye bir şey oluşturuyor. Şimdi bu bir Scheme ifadesi. Eğer siz bunu `eval` yaparsanız, 12 dönecek. 

Yani mesela burada bakalım... `(+ 3 4 5)`... Bu 12 dönecek bu şekilde. Yani biz bunu evaluate etmesek 12 dönecek. Dolayısıyla buna `eval` diyor. `(cons '+ a_list)` diyor, construct ediyor. Ee şimdi bu şekilde yaptığımızda ve bunu evaluate ettirdiğimizde 3, 4, 5'i toplattırmış oluyoruz yani. Aslında `adder`'ı... yani `adder` fonksiyonu kendi içerisinde listeye, yani kendine gelen listenin önüne artı koyup da onu evaluate eden bir fonksiyon olmuş oldu. 

Burada ya tabii bu çok basit bir şey. Burada bunu toplamanın daha mantıklı ve kolay yolları var ama burada bir örnek olarak yani nasıl bir fonksiyon burada yazılabilir, fonksiyon nasıl bir fonksiyon yazıp onu çağırabilir burada bunu görmüş olduk. 

The parameter is a list of numbers to be added. `adder` inserts a `+` operator and evaluates the resulting list. `cons`'u da ne yapıyor? Inserts the atom operator `+` into the list of numbers. Ve tabii quote olması lazım hemen evaluate etmemesi için buraya. Mesela bunu koymazsanız eğer direkt burada evaluate eder. Yani onu yapmaması için... Bir de burada interaction environment koymak gerekiyor yoksa kod çalışmıyor. Öyle bir eksiklik şey var. 

Mesela şurada yapalım. Mesela şimdi şunu paste diyelim. `adder` diye oluştu gördüğünüz gibi. Artık ben burada `adder` deyip... pardon `(adder '(3 5 7))`... `adder` deyip de buraya bir liste yazdığım zaman artık 15 diye döndürüyor. Çünkü ne yapıyor arka planda? `(+ 3 5 7)` yapıyor ve onu da `eval`'a sokuyor, dolayısıyla cevap dönmüş oluyor.

**14:50 - 19:08 (Common Lisp Overview - English & Turkish)**
Şimdi Scheme dışında tabii başka programlama dilleri, functional programming languagelar var. Common Lisp, bunlar da zaten atası. A combination of many of the features of the popular dialects of Lisp around in the early 80s. A large and complex language, the opposite of Scheme. Yani Scheme tabii biraz daha şey, MIT'de böyle biraz functional programming öğretmek için yapılan biraz daha instructional bir dil. Aslında çok büyük geniş özellikleri olan bir dil değil o kadar. 

Ama Lisp tabii kendi dialektlerinin çeşitli özelliklerinden beslendiği için çok fazla şeyler içeriyor. Record, array, complex numbers, character strings, IO capability'leri güçlüymüş, packages with access control, iterative control statements falan böyle bir sürü farklı şeyle donatılmış. 

Macros... create their effect in two steps: expand the macro, evaluate the expanded macro. Yani makrolar yazılabiliyor bunlara girmeye gerek yok şimdi. Some of the predefined functions of Common Lisp are actually macros. User'lar kendileri macro oluşturabiliyormuş. 

Backquote operator, burada şey var, Scheme'den ufak bir farkı, normalde quote yaptığımız zaman evaluation'dan avoid ediyorduk, evaluation yapmamasını sağlıyorduk. Burada bir de bu backquote var, bu da klavyede e'nin üstünde olur ama benim şimdiki klavyem İngilizce olduğu için orada değil. Türkçe klavye de yok yanımda şu anda, göremiyorum nerede ama sanırım e'nin üstündeydi. Sol üst köşede miydi? Evet sol üst köşede bir tarafta olması lazım aynen. 

O backquote operator'ü... o bu yapıldığında şöyle bir şans oluyor sadece, virgülle yapmayacağınız kısmı söyleyebiliyorsunuz. Mesela diyor ki bunu bir liste olarak değerlendir, evaluate etme, fakat virgülden sonra gelen kısımları da evaluate et yani. Mesela burada aynen bu şekilde yaptığımızda, mesela dur bakalım Scheme'de var mı? Bunda yok herhalde... var mı Scheme'de de varmış aslında enteresan. 

Mesela dur yapalım bu Common Lisp kurulu muydu bizde? Kurulu değilmiş kuralım bir taraftan kursun. `sudo apt install clisp`. Kursun... yes diyelim. Common Lisp de kurulsun. Tamam. 

Şimdi Lisp'te de yani bu mesela similar to Scheme's quote except that some parts of the param can be unquoted falan diyor ama burada demek ki bu slaydın hazırlanmasından şimdiye geçen süreye kadar demek ki Scheme'e de bu eklenmiş ki onda da `(a 12 c)` döndürdü. Yani böyle yazdığımızda şurası yapılsın diyoruz. Bu şeye benziyor yani hani `System.out.println` içerisinde böyle quote içerisinde yazdığınızda orası text olarak değerlendirilir ya, ama siz mesela bir kısmını variable gibi düşünüp oraya işlem yaptırmak isterseniz mesela 2+5 falan gibi, o kısmı parantezin dışına çıkartmak zorundasınız. Onun yerine böyle bir şey de yapabiliyorsunuz gibi yani. Mesela şurası hariç falan diyebiliyorsunuz yani. 

Tamam, kuruldu mu `clisp`? Yine mesela burada bu şekilde yaptığımızda yine `(a 12 c)`'ye döndüğünü görüyoruz Common Lisp'te de. Tamam. Reader Macros, Lisp implementations have a front end called the reader that transforms Lisp into code representation. Burada yani yine hep böyle kod içinde kod oluşturup o kodu çalıştırma şeklinde şeyler. Bunu geçelim şimdi. Symbol data type'ı var... The reserved words are symbols that evaluate to themselves. Symbolic matematik yapmak türünde şeyler, onları geçelim şimdi neyse Common Lisp'i geçmiş olalım gençler.

**19:08 - 28:35 (ML Language Introduction and Examples - English & Turkish)**
ML'e gelelim. A static-scoped functional language with syntax that is closer to Pascal than to Lisp. Bakalım bir dakika ML var mı? Buradan da çıkalım. `sml` olması lazım standard ML. Evet `smlnj` kurmamız lazım. `sudo apt install smlnj`. Standard ML of New Jersey miydi öyle bir şeydi. Evet `sml` diyoruz giriyoruz şeyine. Tamam. Bir saniye. Evet. 

Şimdi, ne diyor? Static-scoped functional language with syntax that is closer to Pascal than to Lisp. Biraz daha Pascal'ı andıran bir yapısı var. Uses type declarations, but also does type inferencing to determine the types of undeclared variables. Evet type inferencing yapıyor, determine the types of undeclared variables yapmak için. Yani eğer bir variable'ı declare etmediyseniz onun type'ını anlamak için type inferencing yapıyor. 

It is strongly typed, whereas Scheme is essentially typeless and has no type coercions. Yani burada strongly typed, bir şeyin ne olduğunu yazmamız gerekiyor. Mesela örnek... burada işte n'in integer olması falan gibi. 

Burada yine bakalım... birkaç koda bakalım şurada. Mesela `val radius = 2.7`. Burada tabii şeyle vermemiş ama `2.7` inferencing yapıyor yani bunu double olarak değerlendiriyor mesela falan. 

Şimdi bakalım, it is strongly typed dedik. Does not have imperative-style variables. Its identifiers are untyped names for values. Includes exception handling and module facility for implementing abstract data types. Includes lists and list operations. Genel özellikleri bunlar. 

Bakalım mesela bir tane fonksiyon nasıl yazılıyor? Burada biraz daha bizim bildiğimiz dillere yakın. Yani `fun cube` diyorsunuz o işte parametresi, ondan sonra da `x * x * x`. Bu da bunun implementation'ı oluyor fonksiyonun. The type could be attached to return value. Mesela burada `cube (x : int) : int` derseniz ki bu bizim bildiğimiz dillerde de olan bir şey zaten, eee işte Python'dakine benzer. Burada `x * x * x` döndürüyorsunuz. If with no type specified it will default to int. Hiçbir şey yapmazsanız int'e default yapmışlar. User defined overloaded functions are not allowed, so if we want the cube function for real parameters it would need to have a different name. Overloading yok. Mesela tekrar bir cube fonksiyonu olsun da bu da real sayılar için olsun derseniz mesela böyle `cubeReal` diye farklı bir fonksiyon yazmak gerekiyor yani, function overloading olmadığı için. 

ML selection. If expression then then_expression else else_expression. Mesela burada bir tane factorial fonksiyonu var. `fun fact 0 = 1 | fact 1 = 1`. Matematikteki şey ifadesi gibi yani olur ya böyle $f(x) = 1$ if $x = 0$, $1$ if $x = 1$, işte burada da $n \times (n-1)!$ if otherwise yani. Gibi... güzel yazamadım ama $n \times f(n-1)$. Neyse, tamam. Bunun matematiksel ifadesi gibi. 

Mesela bunu alalım buradan kopyalayayım, gelelim. Paste. Mesela burada artık factorial, illegal token dedi ama burada bir şey bir yanlışlık... copy paste ederken bir yanlışlık yapıyor herhalde ama... `fun fact 0 = 1`... he bir dakika `fact 1 = 1` falan gelmiş içine bir yanlışlık, copy paste ederken sıkıntı çıkıyor. 

Şöyle yazalım: `fun fact 0 = 1 | fact n : int = n * fact(n - 1);`. Mesela bunu yazdığımızda artık elimizde `fact` var. Burada artık `fact 10` falan diyebiliriz yani. Noktalı virgül. Noktalı virgülle bitiyor. Bu şekilde yapılabiliyor. Güzel bir dil.

**23:55 - 28:35 (ML Lists and Attempts at Imperative Loops - Turkish)**
Burada evet `car` ve `cdr`'ın ML versiyonu `hd` (head) ve `tl` (tail). Yani bu aslında head ve tail demek yani daha doğrusu. Yani head, tail. Bunlarda `hd` ve `tl` diye kısaltmışlar. Construct da böyle `::` ile yapılıyor. 

SML'deki `for` loop gibi bir şey yok mu Coursera'daki kursta iterate etmek için hep recursion kullanıyorduk. Ya evet burada mesela şurada şey diyor ya aynı şekilde yani burada da other variables sanki yazıyordu ya yazmıyor mu... pardon yazmıyormuş. Ben sanki bir yerde görmüştüm ama herhalde önceden çalışırken dedi. Eee evet dur bakalım bir saniye aratalım `sml loop`. Loops in smlnj in functional programming. Dur bakalım. 

Mesela dur şöyle bir şey çıktı... ne diyor? Tabi sormuş burada Stack Overflow'da ama if you really wanted to use mutation falan filan burada while, böyle bir şey yapılabiliyor mu acaba sml'de zannetmiyorum function bir deneyelim bakalım. Enteresan. 

Paste anyway. Hım, unbound variable `bar`. Bir dakika copy paste ederken hep sıkıntı çıkıyor burada da. Eşittirler niye öyle oldu? Eşittir falan yeri aa olmadı. Bir şey yapalım şöyle bir saniye. O zaman sadece şey kısmını yazalım mesela diyelim ki `val counter = ref 0;`. Tamam. `while !counter < 3 do ( ... )`. Veya şöyle yapalım bir saniye `val total = ref 0;`. Tamam. `while !counter < 3 do ( total := !total + !counter; counter := !counter + 1 );`. Şöyle yapalım. 

Z define... Şu an walla ben de hatırlayamadım işin içine yapamadım ama dur bakalım bir dakika. Simple loop in sml diyelim. Aratalım loops, evet şurada bir tane çıktı ama... ben bakmamıştım ama daha önce. Simple design bunları yapmaya çalışıyorum for loops typically use to iterate falan filan o kadar da var demiş, sml sanırım yok galiba standard sml has a while loop defined which may be used ha varmış bir dakika. Tamam. Güzel. Şunu yapalım o zaman. Bu ha evet oluyor. Oluyor evet evet oldu. Yani şu kod çalıştı yani. 

`(val x = ref 0; while (!x < 10) do ( x := !x + 1; print (Int.toString (!x)); print "\n" );)`

Buna daha önce bakmamıştım gençler bunu bilmiyorum şu anda ben onun için bunu geçeceğim. Ama var yani `while` loop yapılabildi çalıştı yani gördüğünüz gibi. Hım ilginç bir kod ama bakmak lazım neyse geçelim.

**28:35 - 34:04 (ML Filter, Map, and Currying - English & Turkish)**
Neredeydik şurada ML, ML'de de böyle yine head ve tail bu şekilde yapılıyor. Yani `hd` ve `tl` ile, `cons` da `cons`un karşılığı da burada `::` yani colon colon. 

Yani burada mesela yine aynı şekilde, bu cevabın `car`'ını isteseydiniz 4 döndürecekti, `cdr`'ını isteseydiniz 3 5 7 döndürecekti liste olarak. Yani bu ikisini de `cons` yaparsanız yine bunu döndürecek gibi, birbirinin tersi gibi düşünebiliriz. Yani `cons` ve `car` `cdr`'ı nasıl birbirinin tersi düşünüyorsak şu operatör ve `hd` ile `tl`'ı da birbirinin tersi olarak düşünebiliriz. 

Mesela burada ne yapmış, length, bir listenin length'ini bulmaya çalışırken diyor ki mesela boş küme ise 0 veyahut da length head ve tail olarak ayırırsam diyor ben bunu 1 + length(t) diyor. Yani head'in uzunluğu zaten 1, t'nin uzunluğu da şey... Bu tabii simple list için. Mesela burada iç içe listeler olursa sadece üst düzeyi sayıyor. Yani mesela burada mesela şöyle bir liste varsa, liste şu şekildeyse sadece, tamam bu 3 sayıyor ama mesela bir de şu var tabii bunun da kendi içinde bir liste olması falan durumunda mesela böyle `(a b) (c d)` gibi bir listeyse, 4 demiyor tabii ki, 3 diyor bunun cevabına uzunluğuna 3 diyor, aynı bu şekilde. Eee bunu öyle yapmamak için, mesela burada liste ise h'nin de içini say falan gibi bir şey demek lazım toplam saymak istiyorsak, recursive call atmamız lazım burada 1 yerine. 

Eee burada da mesela iki listeyi birbirine ekleyen şey. Mesela `fun append [], list2 = list2`. Yok eğer öyle değilse de birinci listeyi head ve tail olarak ayır, ondan sonra da de ki h ve şunu construct et. Mesela burada bu şu şekilde çalışıyor. Diyelim ki bizim birinci listemiz `(a b c)`, ikinci listemiz de `(d e f)` olsun. Mesela burada ne yapmış oldu böyle diyerek? Diyor ki, şimdi birinci listemiz boş mu? Değil. O zaman şunu çağıracağız. Şimdi bu a kısmını h olarak değerlendireceğim, şurayı da tail olarak değerlendireceğim, değil mi? List2'yi de şöyle düşüneceğim. Diyor ki o zaman, şunun cevabı `(a b c)` concatenation `(d e f)`, şuna tekabül ediyor diyor. Yani h yani a, `::` append, append diyelim şöyle, `(b c)` ve `(d e f)`. Yani bu şekilde düşünüyor yani. 

Ondan sonra da öyle öyle gidiyor. Mesela ondan sonra tabii bir aşama sonra a b ile a b'nin üstüne c d e f'nin appendini ekle diyor. Ondan sonra a b c'nin üstüne, a b c'nin üstüne boş küme ile d e f'nin appendini ekle diyor. E zaten bu boş küme ile d e f'nin appendi zaten direkt d e f'yi veriyor. Onun için a b c ile d e f'yi, ha bu da d e f'yi verdi a b c d e f olmuş oluyor yani direkt a b c d e f'ye gitmiş oluyoruz. Çünkü burası list2'yi döndürdüğü için artık cevap a b c d e f şeklinde oluşmuş oluyor yani.

İlginç yani böyle recursive yapılan şeyler ilginç oluyor tabii ki. 

The val statement binds a name to a value, similar to define in Scheme. `val distance = time * speed`. Yani burada val is nothing like an assignment statement in an imperative language. If there are two val statements for the same identifier, the first is hidden by the second. Val statements are often used in let constructs. Mesela burada matematikte de işte $let \ x, y \ be \ ...$ falan hani $let \ x=5, y=3$ falan deyip de x ve y üzerinden bir şeyler yaptığımızda mesela öyle bir ön tanım gibi olduğu gibi, burada da yine işte `val radius = 2.7` olsun, `pi` de `3.14159` alalım. O zaman cevabımız işte `pi * radius * radius` falan diyerek dairenin alanını bulduruyor falan. 

Tamam. `filter`, yine aynı şekilde filter var. Higher-order filtering function. Yani mesela işte burada bu listeden sadece 50 niye dönsün ki burada? Pardon. Bir saniye burada... yani tabii ki bu 25 ve 1'i döndürecek. Herhalde yukarıdakinin şeyi miydi? Bir dakika bakalım. Tabii ki 25, 1 döndürmesi lazım tabii ki. Eee evet. Yani... şunu silelim. Şimdi şu yukarıdakini şey yapmışız. Bu herhalde yukarıdakine gönderme yapıyor yani şurada biraz silinmiş olan bir şey var. Burada 25, 1 ve 50 var tabii ki. 100'den küçük olan. Onu yaparsanız bu döner tabii de. Veya şöyle kalsın tamam bu daha mantıklı. `List.filter`. 

Veya şu belki çalışmıyor olabilir mi benim sildiğime göre? Evet error vermiş. Unbound variable filter demiş. `List.filter` demek lazım o zaman. Bir dakika `List.filter` aynen. Bir dakika niye olmadı yine? Hımm, `fn x =>`. Ha evet orada da bir yanlışlık var. Şuradan geri gidebiliyor muyuz? Gidemiyoruz. O zaman şöyle yapalım. Şurada düzenleyelim bunu. `List.filter`, burada da `fn x`'in şu parantezi olmayacak. `fn x => x < 100`, şurada parantezi kapatacağız çünkü bu filter'ımız bizim burası. Ve buna da bunu vereceğiz. Ondan sonra buna da gerek yok. 

Şu şekilde yaptığımızda çalışıyor olması lazım. Bir deneyelim. `List.filter (fn x => x < 100) [25, 1, 711, 50, 100];`. Filter'ımızı oluşturduk, listemizi verdik. Olması lazım, evet şimdi oldu. Tamam bu şekilde yapılabiliyor. 

Buna da şöyle yapalım, this returns şunu buraya alalım. Bu da 25'te 1'i döndürüyor tabii ki. 50 diye bir şey yok. Tamam, evet. Bu şekilde işte `Char.isUpper`'ı falan gibi şeyler yapılabilir. `onlyCapitals` falan gibi şeyler yapılabilir. `fun onlyCapitals xs : string list = List.filter (fn x => ...)` falan filan. Bu yani evet bu işte uppercase'leri falan döndürmek yapılabilir, önemli değil çok basit şeyler sonuçta.

`map`, a higher-order function that takes a single parameter, a function. `fun cube x = x * x * x;`. Yani bunu oluşturduk fonksiyonumuzu. `val cubeList = map cube;`. `val newList = cubeList [1, 3, 5];`. Ve `val newList = map (fn x => x * x * x) [1, 3, 5];`. Bu fonksiyon da 1, 3, 5'i verdiğimizde cevabımızı `newList`'e yazacağız. Dolayısıyla 1, 27, 125 diye oluşacak. 

Evet genel olarak daha böyle matematikteki yakın kullanımlar. The use of lambda expression... `val newList = map (fn x => x * x * x) [1, 3, 5];` ne dedik? Burada da burada anonymous bir fonksiyon üretiyoruz, bir küp fonksiyonu üretiyoruz ve buna 1, 3, 5'i veriyoruz ve mapliyoruz. Dolayısıyla burada da yine 1, 27, 125 oluşacak.

Composition'da unary operator `o` ile yapılıyor. Tamam, bunu geçelim. Önemli değil. 

Currying'de şey... yani Currying dediğimiz şey genelde functional programming'in temel şeylerinden bir tanesi. Replaces a function with more than one parameter with a function with one parameter that returns a function that takes the other parameters of the original function. Yani mesela burada eee bir örnek verecek olursak, mesela burada iki tane parametre alıyor bu. Bunu bu şekilde a+b diye yapmak değil de mesela `addA` şeklinde bir fonksiyon yapıp, b'yi de ona parametre olarak almak şeklinde yani. 

A function with one parameter a returns a function that takes b as a parameter. Yani burada nasıl implement edildiğini şu şekilde görebiliriz aslında. Burada mesela bu, bu muydu? Bu değil pardon. Curried functions can be used to create new functions by partial evaluation. Mesela şunun gibi, işte öyle diyelim yani `fun add5 x = x + 5;` mesela 5'le toplayan bir fonksiyon x aldığı zaman onu x+5 döndürüyor. Biz mesela bunu şey yapabiliriz yani on the fly bir şekilde yani `add`'in önünde 2 tane parametre alan bir fonksiyon yazdığımızda, öncelikle `add a` diye bir fonksiyon bunun içinde oluşturtup, ondan sonra ona b'yi verebiliriz. Böyle yaptığımızda currying yapmış oluyoruz yani. Process of currying replaces a function with more than one parameter with a function with one parameter that returns a function that takes the other parameters of the original function. Yani genel olarak şu mantığı bilmemiz yeterli. 

ML functions actually take just one parameter. If more are given, it considers the parameters as a tuple. Commas required. Yani ML'in genel design prensibiymiş bu. Yani ML fonksiyonları her zaman tek bir tane parametre alıyormuş aslında arka planda. Birden fazla aldığında da onu currying yaparak birleştiriyormuş arka planda. Onu anladık.

**34:04 - 42:30 (Haskell Introduction - English & Turkish)**
Geldik Haskell diline. ML'e benzeyen, static-scoped olması, syntax'ı benziyor, strongly typed, type inferencing olması, pattern matching olması falan. Bazı açılardan farklı. Purely functional bir dil Haskell. No variables, no assignment statements and no side effects of any kind. Yani bu tamamen functional bir dil.

Ufak tefek farkları, mesela burada factorial `fact 0 = 1`, `fact 1 = 1`, `fact n = n * fact (n-1)` diye basit tanım bu şekilde yapılabiliyor yani Haskell'de. Güzel. 

... [The video ends while discussing Haskell pattern matching examples] ...
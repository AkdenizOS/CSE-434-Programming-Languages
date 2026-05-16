Here is a detailed report and transcript of the video you provided.

# Video Analysis Report

**Topic:** Functional Programming Languages: Haskell and F#, and a Comparison with Imperative Languages

**Overview:**
This video is a recording of a lecture on programming languages, with a strong focus on the functional programming paradigm. The instructor uses a combination of presentation slides and live coding demonstrations in a terminal to explain key concepts. The primary language discussed is Haskell, followed by a brief overview of F#, and concludes with a comparison between functional and imperative programming styles.

**Key Segments & Content:**

1.  **Introduction to Haskell (00:09 - 05:19):**
    *   The instructor introduces Haskell as a purely functional language, distinguishing it from ML by its lack of variables, assignment statements, and side effects.
    *   He demonstrates basic function definitions, using the `factorial` function as a primary example, showing how it can be defined recursively and with pattern matching.
    *   He introduces the interactive Haskell environment, GHCi, and uses it to run code snippets.
    *   The lecture covers Haskell lists, including list notation, length calculation, arithmetic series generation, and concatenation using the `++` and `:` (cons) operators.
    *   The instructor recommends the online resource "Learn You a Haskell for Great Good!" for further study.

2.  **Quicksort in Haskell (05:20 - 15:29):**
    *   A significant portion of the lecture is dedicated to explaining the Quicksort algorithm implemented in Haskell.
    *   The instructor highlights the conciseness and elegance of the Haskell implementation compared to traditional imperative versions.
    *   He explains the logic line by line: picking a pivot (the head of the list), filtering elements smaller than the pivot into one list, filtering elements larger into another, recursively sorting both, and concatenating the results.
    *   He attempts to write the Quicksort function directly in the GHCi terminal but encounters syntax errors due to multi-line definitions. He resolves this by writing the code in a separate file (`a.hs`) and loading it into the interpreter to demonstrate its functionality successfully.

3.  **Lazy Evaluation (15:30 - 23:58):**
    *   The concept of lazy evaluation is introduced, explaining that a language is non-strict if it doesn't require all parameters to be fully evaluated before function execution.
    *   He demonstrates how this allows for interesting capabilities like defining infinite lists (e.g., `positives = [0..]`).
    *   He provides an example of a function checking if a number is a perfect square, showing how a naive implementation could lead to an infinite loop, and how it can be rewritten to work safely with infinite lists by adding a boundary condition.

4.  **F# Overview (23:59 - 27:53):**
    *   The instructor briefly moves to F#, describing it as a .NET functional language based on OCaml.
    *   He notes that while fundamentally functional, it supports imperative features and Object-Oriented Programming (OOP) to interoperate with other .NET languages.
    *   He quickly touches upon features like sequences, iterators, and sets.

5.  **Functional Features in Imperative Languages (27:54 - 34:42):**
    *   The lecture discusses how functional programming concepts are increasingly "creeping" into imperative languages.
    *   Examples are given of anonymous functions (lambda expressions) in JavaScript, C#, and Python.
    *   The instructor shows how Python supports higher-order functions like `filter` and `map`, and partial function applications.
    *   Ruby's blocks are also presented as a way to achieve functional-like behavior.

6.  **Comparing Paradigms (34:43 - 42:33):**
    *   The instructor concludes by comparing imperative and functional languages.
    *   He states that imperative languages generally offer more efficient execution because they map closely to the underlying von Neumann machine architecture. However, they suffer from complex semantics and syntax.
    *   Conversely, functional languages have simpler semantics and syntax, being closer to mathematical expressions (and thus more human-readable), but they often have less efficient execution because the compiler has to do more work to translate them into machine code.
    *   The video ends with a summary slide and the announcement of a break.

---

# Detailed Transcript

**00:00** Tek tane parametre alıyormuş aslında arka planda. Birden fazla aldığında da onu currying yaparak birleştiriyormuş arka planda, onu anladık.
**00:09** Geldik Haskell diline. ML'e benzeyen, static scoped olması, syntax'ı benziyor, strongly typed, type inferencing olması, pattern matching olması falan.
**00:22** Bazı açılardan farklı. Purely functional bir dil Haskell. No variables, no assignment statements, and no side effects of any kind. Yani bu tamamen functional bir dil.
**00:36** Ufak tefek farkları mesela burada factorial 0 = 1, factorial 1 = 1, factorial n = n * factorial(n - 1) diye basit tanım, bu şekilde yapılabiliyor yani Haskell'de, güzel.
**00:53** Haskell'de kullanmak için GHCi veya exit diyelim, exit bu şekilde mi yazılıyordu burada? Neyse, şuradan bir daha açalım.
**01:06** Evet... Şimdi burada mesela `ghci` diyelim. Tamam yüklü değil, bu yüklü tamam güzel. Bu Haskell compiler.
**01:21** Yoksa şey diye kurabilirsiniz yani `sudo apt-get install ghc` diye kurabilirsiniz, i'yi koymuyorsunuz herhalde install ederken. Zaten size söyler yani.
**01:36** Evet. Mesela burada bir tane yazalım. Bu şekilde, paste anyway...
**01:49** Bunları, bir saniye, üç tanesini yazalım. `fact` factorial n... `n == 0 = 1`... `n == 0 = 1` or `n == 1 = 1` or `n > 0 = n * fact(n - 1)`
**02:21** Aslında 1 demek daha mantıklı ama eşittir buna 1 diyelim, `= n * factorial(n - 1)`. Bakalım olacak mı?
**02:37** Evet. `factorial 5` diyelim. 120. Evet bu şekilde yapılabildi. Kopyala yapıştır ederken nedense bir sıkıntı çıkıyor. Tek satır satır yaparken.
**02:50** Neyse. Bu şekilde yapılabiliyor bunda da. Yani bir fonksiyon tanımında, fonksiyonun parametresi ve işte koşullara göre ne olduğu, yani 0'sa 1 dönecek, 1'se 1 dönecek falan gibi.
**03:09** Polymorphism'i support ediyormuş. This works for any numeric type of x. Square'in ne olduğu.
**03:17** Haskell'de listeler nasılmış? Normal diğer dillere, Python'dakine benzer şekilde yazılıyor, tamam.
**03:28** Length'i bulmak için bu operatörü kullanabiliyoruz.
**03:34** Arithmetic series with the `..` operator. Yani `[4..10]` diye böyle koyduğumuzda direkt, tabii burada şey, 2, 2'şer 2'şer atla şeklinde de verilebiliyor. `[2, 4..10]` 2, 4 ile başladığı için o şekilde gidiyor. Yani bu Excel'dekine benzer bir mantık sanırım. Yani `[2, 4..10]` dediğinizde `[2, 4, 6, 8, 10]` olduğunu arka planda demek ki anlayabiliyor. Deneyelim. İlginç. Bu da, güzelmiş.
**04:08** `[1, 3] ++ [5, 7]` concatenation. Concatenation. Neyse.
**04:16** Cons, car, cdr via the colon operator. Burada yine `1` ile `[3, 5, 7]` listesini birleştirme, yani cons yapma işlemi bu şekilde olabiliyor.
**04:30** Bu şekilde devam ediyor bazı özellikleri. Bunlara zaten icabında bakılabilir.
**04:34** Şeyde bir tane çok güzel bir site vardı. "Learn You a Haskell" learnyouahaskell.com diye. Hala duruyordur umarım. Evet böyle bir site var gençler.
**04:47** Burada "Read it online", hem kitabı var, internetten bulabilen, hem de burada son derece güzel bir şekilde anlatıyor yani her şeyi. Baktığımızda kodlarla örneklerle uzun bir şekilde hepsi burada var. Buradan çok güzel Haskell öğrenilebilir yani. Bu da burada dursun. learnyouahaskell.com. Adres bu, arasanız çıkar. Tamam.
**05:19** Mesela bir Quicksort örneği. Çok pratik. Dikkat ederseniz inanılmaz pratik bir Quicksort implementation'ı.
**05:27** `sort [] = []` boş ise boş olsun. `sort (h:t) =` ... `h:t` Şimdi burada Quicksort'u, algoritma dersi gördünüz mü, görmüşsünüzdür herhalde 3. sınıf 2. dönem, değil mi bu? Orada Quicksort'ta biliyorsanız şey var, pivot seçimi var. Bir tanesini seçiyorsunuz, diğer elemanları ondan küçük, büyük mü diye ikiye ayırıyorsunuz. Böyle böyle recursive olarak gidiyorsunuz.
**05:51** Burada da mesela pivot seçimini... Aslında Quicksort'ta pivot seçimi bildiğiniz gibi enteresan bir iş. Yani aslında normalde biraz daha zekice seçmek lazım. Mesela bazen rastgele 3 tane seçip ortanca median alınabiliyor. Çünkü onun daha orta bir sayı olma ihtimali daha yüksek.
**06:14** Çünkü Quicksort'ta biliyorsunuz pivotu seçerken rastgele seçerseniz ve zaten en küçük eleman falan çıkarsa yaptığınız ikiye ayırma işlemi neredeyse boşa gitmiş oluyor. Onun için olabildiğince orta bir değer, yani sayıları olabildiğince ikiye bölecek bir değer seçmek çok önemli pivottan.
**06:31** Ama burada çok basit yazmış. Yani önemli değil. Sonuçta bu da çalışacak bir algoritma.
**06:36** Burada ne yapmış? Head'e göre ayırmış. Yani ilk baştaki elemanı, aldığı listenin ilk elemanını pivot gibi düşünmüş. Ne yapıyor? Aldığı listeyi `h` ve `t` olarak görüyor önce bir, yani birinci elemanı ve geri kalanı diye.
**06:49** Ondan sonra diyor ki `sort`... burada filter koymuş. Yani `b` öyle ki, yani öyle `b`'ler ki, `h`'den küçükse buraya koy. `t`'nin `b`'den küçük olan, şey `h`'den küçük elemanlarını bu `b`'ye koy diyor. Yani `t`'nin içindeki `h`'den küçük olan elemanları `b`'ye koy, pardon `h`'den küçük olan elemanları `b`'ye koy ve bunu `sort` ediyor. `sort` da zaten recursive call dikkat ederseniz.
**07:25** `h`'yi ortaya koyuyor, ondan sonra bir de `h`'den büyük olanları sıralıyor. Yani mesela burada işte `[4, 5, 2, 1, 7, 8]` gibi bir liste verildiğinde ne yapıyor? Burası `h` olsun diyor. Şu kısım `t` olsun diyor. Değil mi? Burada bunu bu şekilde ayırıyor.
**07:45** Ondan sonra diyor ki `h`'den küçük eşit olanları diyor bu tarafa koy. Dikkat ederseniz küçük derse şey olur... Burada ufak bir aslında şey var. Yani burada 4'ü iki defa oluşturabilir yani nihayetinde çünkü 4'ün kendisini de sola koyar bir de ortaya koyarsa 4 ikilenmiş olur aslında ama. Öyle neyse, onu tam düşünemedim şu anda, yapmıyor olabilir.
**08:19** Doğru, şöyle diyor aslında: `sort` diyor, 4'ten küçük olanlar yani 2 ve 1'i buraya koyuyor, 4'ü ortaya koyuyor ve buraya da 5, 7 ve 8'i koyuyor. `sort [5, 7, 8]`'i koyuyor. Yani yaptığı şey bu. Bunlar tabii yine kendi içinde devam ediyor yani kopya devam etmeye, ta ki bir taraf boş olana kadar orası bitiyor, diğer taraf da boş oluyor, orası da bitiyor filan. Bu şekilde recursive kol atılmış oluyor.
**08:46** Deneyelim. `sort`... Mesela diyelim ki `sort [] = []` olsun. Ondan sonra `sort (h:t) = sort`... şöyle yapalım. Bir saniye.
**09:10** `sort`... `b` öyle ki `b`... Şöyle yapacağım bunu. `t; b <= h` ondan sonra `++ [h] ++` ... yine `sort`.
**09:34** Ben burada devam edeceğim. `b | b <- t; b > h` dediğimizde, bakalım şu oklar da doğru yaparsa... Hmm noktalı virgülde hata verdi.
**09:59** Burada bir hata var. Hmm... `b <- t` desek. Bu defa da eşittire hata verdi.
**10:29** Neyse burada bir şey var ama bunun... Ha pardon, ben bunu kendim yapmış mıyım? Tamam, tamam, ben bunu yapmıştım zaten. Hah tamam.
**10:38** Ben bunu önceden çalıştırmıştım ben bunu, bu olmayınca hazırlamıştım onu unutmuşum. Tamam. Quicksort burada ne yapıyoruz? Evet. Quicksort yazıyoruz. Ee bu şekilde Quicksort... burada `head` ve `tail` yerine `p` ve `xs` diye isim verdim. Tamam.
**10:59** `quicksort lesser` ve `quicksort greater` diye iki parça. `lesser` ve `greater`'lar da `lesser = filter (< p) xs`, `greater = filter (>= p) xs` diye yazılarak `where` operatörü kullanarak burada yapılabilir. Mesela bunu alalım. Deneyelim burada.
**11:21** Yani bunu yine böyle tek tek yazmak mı gerekiyor? Haskell... O zaman şöyle yapalım. Bununla uğraşmayalım bir dakika. Eee Ubuntu, tekrar şunu açayım. Ya da nasıl çıkarken biraz kötü oluyor.
**11:35** `cd PL`, `cd` şunu da toparlayayım diyeyim. Burada mesela `nano a.hs` diyelim. Yapıştıralım bunu.
**11:46** `ghci a.hs` diyelim. Loaded diyor. Mesela burada artık `quicksort`... `quicksort [6, 3, 7, 9, 1]` falan yapsak mesela bu şekilde... Eee pardon. `quicksort [6, 3, 7, 8]` filan desek.
**12:18** Bu nasıl? Şöyle yapalım. Tamam. `quicksort [6, 7, 8, 1]` filan diyelim şöyle. Bu da olmadı. Bu listeyi, listeyi şöyle yapalım...
**12:59** Virgül, virgülle yazalım. Şöyle yapalım `quicksort [6, 1, 4]` filan diyelim. Hah şimdi oldu. Evet tamam tamam, bir şey olması gerekiyordu. Tamam.
**13:19** Evet, bu şekilde oldu. Yani `exit`... Buradan nasıl çıkıyorduk çoğundan burada? Ctrl+D mi? Hah Ctrl+D imiş tamam.
**13:36** Yani burada `nano a.hs` dediğimizde bu şekilde yapıldığını gördük, tamam.
**13:44** "En küçük eleman ilk başta verilirse ne olacak?" Evet evet. Yani evet, orada en küçük eleman ilk başta verilirse şöyle olmuş oluyor, o tur boşa gitmiş gibi oluyor aslında. Mesela şurada işte bize mesela `sort [1, 9, 6, 3, 7]` gibi bir şey gelse. Ne olmuş olacak, bu pivot oluyor. Bu pivotu ortaya koyuyoruz, bu taraf boş oluyor, yani `sort []` küme. Ondan sonra `sort [9, 6, 3, 7]` gibi inefficient bir hal alıyor ama yine de sonuçta 1'den kurtulduğumuz için sonra tekrar devam ediyor yani. Bu inefficient bir şey oluyor yani.
**14:24** Quicksort'u $n^2$ yapan bir şey bu. Zaten Quicksort'un şeyinin $n^2$ olmasının sebebi bu. O $n^2$ olmasının sebebi pivotun böyle en küçük veya en büyük filan olabilmesi yani. Öyle bir illa ortadaki bir median'ı seçme şansımız olsaydı sürekli, Quicksort zaten $O(n \log n)$ olurdu. İşte o yüzden $O(n \log n)$ olamıyor, $O(n^2)$ oluyor yani.
**14:50** Ama o kurtarıyor yani gördüğün gibi. Mesela 1'i buraya başa koyuyor. Ondan sonra burayı sort ediyor, bunları concatenate ediyor yani sonuçta. Boş string, 1, ve şunların sort edilmiş hali, yani 3, 6, 7, 9 diye gelecek bu da, nihayetinde sort edecek. Evet.
**15:12** "Sen dedin tabi şey... şu 1'i tekrar şeye dahil etseydi, buraya dahil etseydi evet sonsuz loop'a girerdi ama bu artık bundan, 1'den kurtulduğu için artık 3, 6, 7, 9 üzerinde çalışacağı için, yani 9, 6, 3, 7 üzerinde çalışacağı için kurtarıyor yani."
**15:30** Lazy evaluation. Diğer bir önemli şey, kavram functional dillerde. Lazy evaluation aslında bazı diğer şeylerde de var yani mesela, gerektiğinde hesaplama. Mesela Java'da da mesela `if (n == null || n.val == 3)` falan... mesela diyelim ki bir linked list'te ilerlerken böyle bir şey diyorsunuz ya mesela, eşit değildir bunu pardon. `&&` diyelim buraya da. `&&` diyelim tamam mı?
**16:04** Yani mesela bu ne demek? Bu node null değilse ve valuesu da 3'se. Mesela şimdi burada normalde null olanlarda burayı yapsa bu da bir shortcut deniyor buna ama yani biraz da şey aynı mantık. Bu yani gerekmediğinde çağrılmıyor yani. Gerekmediğinde, en son durumda... Ya bu aslında lazy evaluation örnek olarak verilemeyebilir pardon. Ama neyse yani sonuçta lazy evaluation şu demek: Bir şeyi sadece ihtiyacı olduğunda çağır demek.
**16:31** A language is strict if it requires all actual parameters to be fully evaluated. A language is non-strict if it does not have the strict requirement. Non-strict languages are more efficient and allow some interesting capabilities - infinite lists gibi.
**16:45** Lazy evaluation only compute those values that are necessary. Positive numbers mesela diyor ki, mesela şöyle bırakabiliyormuş: `positives = [0..]`. Yani sonsuza gidiyor, yani ilginç. Yani sanki sonsuza giden bir şey yapmış gibi.
**17:00** Determining if 16 is a square number. Ne diyor? `member [] b = False`. `member (a:x) b = (a == b) || member x b`
**17:28** Yani önce bir `a` `b`'ye eşit mi diye bakıyor. Ve eşitse tamam güzel. True dönecek, yani member, member'mış true dönecek. Değilse de `x`, `b`'nin içinde mi diye bakıyor. Yani pardon `b`, `x`'in içinde mi diye bakıyor. Yani işte `[5, 6, 9, 2]`'nin içinde mesela biz 3'ü arıyorsak, pardon, çok enteresan...
**18:04** (Sessizlik)
**18:05** Sesim geliyor mu gençler?
**18:08** - Geliyor hocam sesiniz.
**18:10** Bir ara gelmedi ama değil mi biraz önce? Ya ben 'Do not disturb' aldım ama niyeyse WhatsApp araması gelince beni şeyden atmış yani, ilginç. Normalde 'Do not disturb' onu da yok etmesi lazım ama neyse.
**18:27** Tamam. Eee... Şimdi ne diyorduk? Evet, burada mesela `[5, 6, 9, 2]`'nin içinde 3'ü ararken işte 3'le 5 eşit mi diye bakıyor, değilse `[6, 9, 2]` arasında içinde arıyor yani gibi.
**18:48** Ve burada squares'de mesela square number'ları da şöyle tanımlamış: Söyleyebiliyor mesela işte `n * n` ve `n` sıfırdan sonsuza giderken yani, enteresan. `member squares 16`. Mesela 16 bir square number mı dediği zaman bu fonksiyonu bu şekilde kullanabiliyormuş. Enteresan.
**19:13** Yani `squares` kümesi, bakarsanız sonsuz bir küme, `[0..]` denmiş. Burada da `member x b`... Mesela bu call'u attığında nereye kadar gidecek değil mi? Member... yani enteresan bir şey aslında nereye kadar gidecek `member squares 16`. Mesela ben 17 yazsaydım ne olacaktı buraya mesela, 17'yi bulamadıktan sonra atlayıp gidecek miydi değil mi?
**19:50** Mesela bakalım bir dakika bunu merak ettim ben de. Nasıl yapacak? Şeyimiz nerede? Şimdi `member`... hatta şunu şöyle alayım ben, copy.
**20:05** Şuradan çıkalım. `nano m.hs` diyelim, paste edelim. Çıkalım. `ghci m.hs`. "Parse error on input 'b' Use spaces instead." Ha bir dakika, şeye hata verdi. `nano m.hs`... şurada bunu böyle yapmamız gerekiyor.
**20:45** Nerede? "No modules loaded." `member`... bir saniye şöyle yapalım.
**21:03** Şurada yapalım. `ghci`, bir saniye... `member [] b = False`. Şunu yapalım. Evet, sıkıntı yok. `squares`'i bu şekilde tanımlayalım.
**21:26** A, bir dakika bu, pardon. Şöyle mi yapacağız bunu? Hah, tamam. Orada hata verdi. Tamam.
**21:41** `member squares 16`. Mesela bu `True` döndü. Şimdi peki ben `member squares 17` yaparsam? Hah, evet tahmin ettiğimiz gibi sonsuza kadar gidiyor. Enteresan yani bu tabii biraz şey, eee... soru işaretli bir şey ama neyse, sonsuza kadar gidiyor yani, enteresan. Bunu interrupt etmemiz gerekecek.
**22:08** Lazy evaluation'a bir örnek olarak, ama tabii şey, yani burada bu şekilde bir liste oluşturulabiliyor yani, sonsuza kadar aramaya devam ediyor, enteresan, bazen lazım olabilir. Hani bitmesin... hani bazen oluyor ya pi'nin şeylerini hesaplıyorlar, pi'nin basamaklarını hesaplıyorlar, bir yerde kendileri durduracak belki de, bilmiyorum, bir milyarıncı basamağa geldiğinde belki kendisi durduracak.
**22:36** Öyle durumlarda belki, veya işte belli bir yeri geçince durduracak kendisi, bir şeyi bulunca... belki bir özellik sağlaması beklenen bir sayı var, belki oraya varınca kendisi durdurması isteniyor, öyle durumlarda mesela kullanılabilir bu. İlginç.
**22:50** Evet. "If the parameter to squares was a perfect square; if not, it will keep generating them forever. The following version will always work."
**23:02** Mesela `member2` demiş `m (n:x)`. Ne diyor? `m < n`, `member2 n x`. `m == n` ise `True`, `otherwise False`.
**23:13** Yani `m`'nin önce bir `n`'den küçük olup olmadığına bakıyor `member2 n x`. Burada tabii biraz daha güvenli olmuş oldu. Eee, şöyle yapalım.
**23:25** `member2`... `ghci`... bunu yapalım. `member2 n (m:x)`... a bir dakika bu, pardon. 'Variable not in scope member2'.
**23:55** Neyse şey, herhalde baştan başlamak gerekiyor şunlardan falan, neyse geçelim.
**24:02** F#. OCaml, based on OCaml imiş, which is a descendant of ML and Haskell. Fundamentally a functional language, but with imperative features and supports OOP. Has a fully-featured IDE.
**24:16** F# tabii .NET içerisinde olan bir şey. Yani C# gibi düşünün yani şeyin fonksiyonel dili, .NET'in functional dili gibi düşünülebilir yani. Birçok şeyi içeriyor, yani bu aslında nasıl C# biraz böyle C ve Java'nın üzerine build edilmiş hani onların özelliklerini içeren bir şeyse, bu da biraz diğerlerinden esinlenerek yapılmış bir şey, bir dil.
**24:46** Sequences, böyle şeyler var. "Generation of sequence values is lazy." Yine bu şekilde yapılıyor. Sets, yani bu şekilde yaptığında mesela bir milyona kadar filan diye böyle tanımlıyormuş bunu.
**25:01** "Default stepsize is 1, but it can be any number." Mesela burada `1..2..7` diye gidiyormuş. İkişer ikişer artsın dediğimiz zaman, bu MATLAB'ta filan da olan bir şey, biliyorsunuz.
**25:13** Iterators, "not lazy for lists and arrays". Bazı şeyler için lazy yapmıyor. Kendisi direkt yapmış oluyor bunu, kullanıyor. "Cubes sequence for `i` in `1..4 -> (i, i * i * i)`". Bu ne yapmış oluyor? Böyle tuple'lar oluşturmuş oluyor, `(1, 1), (2, 8), (3, 27)` filan diye tuple'lar oluşturmuş oluyor. Evet.
**25:51** Functions. Fonksiyonlar bu şekilde. Ya bunları da aslında geçebiliriz hızlı bir şekilde, burada çok da artık böyle şeyleri çok konuşmanın anlamı yok aslında şey yani icabında açılıp bakılan şeyler olduğu için burada derste konuşmak çok şey değil. Hatta sıkıcı oluyor burada, enteresan bir şey var mı diye bakalım sadece.
**26:11** Pipeline, ha pipeline'lar var. Bildiğimiz tarzda. List filter. "Return value is `[10; 20]`".
**26:30** Burada da `fun n -> 5 * n`. 5 * n'ler 5, 10, nasıl yaptı? 5, 10, 15, 20 diye gidiyor. İşte 5'i, 15'i filan atıyor tabii, 10 ve 20'yi alıyor sadece tek çift olanları alıyor yani şundan dolayı.
**26:50** Functional operators, composition'ı bu şeyle yapıyor evet bu işaretle yapıyormuş F#'ta.
**27:03** Curried functions, `let add a b = a + b` dediğinde `let add5 = add 5` yapıyor yine böyle arka planda, demek ki bir tanesi 5 olunca.
**27:16** Bunları geçelim. Evet, "Why F# is interesting?". Evet bunlar önemli şeyler, böyle slaytları ben seviyorum. Niye önemli, anlatıyor.
**27:25** "It builds on previous functional languages. It supports virtually all programming methodologies in widespread use today." Yani Microsoft'un yaptığı, bu C#'da da benzer diyorum ya, yani yapılan her şeyi almışlar koymuşlar yani dilin içine.
**27:40** "It is the first functional language that is designed for interoperability with other widely used languages." "At its release, it had an elaborate and well-developed IDE and library of utility software." Evet.
**27:54** Support for functional programming in primarily imperative languages. Geldik şimdi şeylere, bizim normal bildiğimiz diller içindeki functional kullanımlara.
**28:07** Anonim fonksiyonlar, mesela C#'ta filan, mesela JavaScript'te "leave the name out of a function definition". Yapılabiliyormuş, evet.
**28:17** C#'ta yine bu şekilde, "returns true or false depending on whether the parameter is even or odd". Yani i'yi bir şeye mapliyoruz, neye? Çiftse sıfır.
**28:32** Python'da lambda varmış. Direkt lambdayı implement etmişler. Bugünlerde neden F# kullanılmıyor?
**28:39** Yani işte şey, şöyle bir şey mesela, her yerde C#, yani C# ve Java da kullanan var sonuçta. Yani bütün özellikleri alıp koymak "not necessarily a good thing" yani bazen. Bazen ne bileyim diğer diller de çok güçlü zaten yani.
**28:59** Kullanan yerler de var F# ama yani öyle çok şey değil. Yani bir de insanlar tabii alışmışlık şeyi var yani, yazılım dünyasında bilinen diller var. Java var, C var, Python var. Yani çok bilinen, herkesin anlayabileceği, hiç kimsenin yabancı olmadığı. Yani bir çalışanı işten çıkarıp başkasını aldığınızda devam edebileceği belli başlı diller var. Ve de çok iyi tasarlanmış diller gerçekten, enterprise'daki lazım olan her şeyi yapabileceğiniz diller.
**29:34** Functional diller biraz daha böyle şey, spesifik. Yani mesela bir proje içerisinde öyle bir kısım var ki, orayı mesela functional yapmak daha mantıklı. Öyle yerlerde kullanılan şeyler yani. Bir projenin bir kısmında filan. Onu bilen olur o company içerisinde, yapar yani.
**30:00** Genelinde tabii, genelinde daha herkesin hakim olduğu bir dili kullanmak daha şey, güvenli bir şey için, company için yani.
**30:10** Python supports the higher-order functions `filter` and `map`. Python'da bunlar var. Bunlardan zaten hatta konuşmuştuk sanırım. Map lambda bu şekilde yapabiliyoruz, map kullanıyorsunuz. Burada lambda anonim fonksiyon üretiyorsunuz küp alan ve bunu apply ediyor yani bu. Return's.
**30:29** Python supports partial function applications. `from operator import add`. `add5 = partial(add, 5)`. "The first line imports add as a function." `add5(15)`. Yapılabiliyor, yani bunlar evet, tamam.
**30:44** Support for functional programming in primarily imperative languages. Ruby'de, Ruby'de var, Ruby blocks. Lambda, mesela ne demiş? `|a, b| a * b`. A, b alıyor, a * b döndürüyor.
**30:58** Use, `times` mesela şöyle `times = lambda` demiş. Bu şekilde tasarlamış. Yani onun da Ruby'deki syntax'ı da bu şekildeymiş yani lambda syntax'ı. `times.call(3, 4)` dediğimiz zaman, ilginç bir kullanım tabii pek alışık olmadığımız tarzda bir kullanım. `times.call(3, 4)`.
**31:22** `times.curry(5)`, mesela biraz önce `times` vardı, `times5 = times.curry(5)` dediğiniz zaman, eee onun üstüne ekliyor. Yani `times5`'ın üzerine eee 3'ü de katınca, `times` da zaten çarpma işlemiydi, dolayısıyla 3'ü 5'in üstüne çarp demek oluyor yani bu. Bu curried oluşturuyor en başta 5 ile. Yani sonuçta, üzerine bir şeylerin çarpılmasını bekleyen 5 diye bir şey var yani burada `times5` diye. O da 3'le çarpınca 15 ediyor yani.
**33:42** İlginç yani. Biraz tabii şey, yani bizim gibi imperative dillere alışmış insanlara çok pratik gelmiyor bunlar ama neyse yani. Eee nasıl diyelim, functional dillerin içine biraz daha gömüldüğümüzde lazım olacak şeyler tabii ki yani.
**34:03** Şimdi gelelim functional ve imperative dillerin karşılaştırmasına. Imperative languages: Efficient execution, complex semantics, complex syntax. Yani execution efficient, çünkü zaten von Neumann architecture'a uygun, instruction'ların çalıştığı şekilde yazıyorsunuz zaten kodu. O açıdan zaten şey hızı daha fazla.
**34:25** Yani burada şöyle aslında, şöyle diyebiliriz, yani burada makine var, machine, burada insan var, human diyelim. Burada işte imperative language'ler human'a biraz daha yakın, onun için burada şu kısmı biz makineye yaptırttığımız için biraz tabii efficient olmuyor yani. Pardon, tam tersi, imperative language'ler makine diline daha yakın. Buraları insan düşünerek güzel güzel, makine diline yakınlığı ister istemez düşünmek zorunda kalarak, imperative language'ler yakın olduğu için, instruction instruction gittiği için.
**35:10** Çok daha efektif kod yazabiliyorlar, insan düşüne düşüne güzelce yazıyor yani, neredeyse machine language yazıyoruz neredeyse. Dolayısıyla buradan buraya interpret eden makinenin yaptığı kısım, compiler'ın yaptığı kısım çok az bir iş ve efficient oluyor tabii ki yazılan kod.
**35:30** Ama functional programming, human'a daha yakın olduğu için, bizim dilimize, matematiğe daha yakın olduğu için, geride yapılması gereken çok iş kalıyor yani compiler'a. Dolayısıyla compiler'ın yapacağı o kompleks ve uzun iş sonucunda elde ettiği kod tabii biraz daha düşük efficiency'ye sahip oluyor yani. Buradaki fark bu. Efficient execution ve complex semantics, complex syntax, e hepsi bunu ifade ediyor aslında.
**36:00** Complex semantics ve syntax dediğimiz şey, imperative dillerdeki şu uzun kısmı gösteriyor. Yani imperative dil yazarken biz mesela for loop'u insan olarak biz for loop'u düşünüyoruz yani, mesela diyelim ki faktöriyel yazacaksın, `n = n * factorial(n - 1) * n` yani sonuçta, matematiksel ifadesi çok kolay bir şey bunun. Ama biz bunu imperative dilde yazarken loop yapıyoruz yani elimizle insan oturuyor loop hazırlıyor. Bu ne demek? Biz bunu machine language'e yakın bir şekle çevirmeye çalışıyoruz. O yüzden semantic ve syntax karışık yani. Ama efficient execution.
**36:39** Concurrency is programmer designed. Concurrency'yi kendiniz yazıyorsunuz, thread'ler process'ler falan kendiniz açıp yazıyorsunuz. Functional dillerde bunların hepsi arka planda yapılan şeyler oluyor. Simple semantics, simple syntax but less efficient execution. Bunların tersi zaten bu da. Aynen, terslerini yazmışlar zaten.
**36:59** Yani Java, F#, SML falan gibi dillerden daha mı efficient? Genel olarak öyle diyebiliriz tabii, imperative diller tabii ki daha efficient yani, şu sebepten dolayı, yani makinenin yaptığı machine diline çevirme işlemi daha az bir şey, onun için insan oturup istediği kadar hızlı bir şekilde yazabilir yani onu.
**37:20** Ama siz functional programming yazıyorsanız... Functional programming'in olayı yani hatta matematikçiler falan muhtemelen daha kolay öğrenir functional programming'i, veya matematiğe daha çok kafası çalışan insanlar, matematiğin daha çok haşır neşir olmuş insanlar fonksiyonlarla falan, her şeyi fonk... Mesela, aslında herkesin illaki matematikçi olmasına gerek yok da, geçen hafta söylemiştim galiba. Biz ortaokulda lisede matematiğe çok maruz kaldık yani. Hepimiz yazmışızdır, f(x) = 1 if x = 1 falan, 2 if x > 1 falan, böyle matematiksel ifadeler yazmayı çok biliyoruz yani biz.
**37:58** Biz hatta dedim ya, üniversiteye başladığımızda biz mesela programlama olarak, imperative dil yerine functional dillerle başlanılsaydı, anlaşılması herhalde daha kolay olurdu yani. Çünkü direkt matematiğin... human'ın yaptığı iş çok daha az bir şey, direkt yazıp geçiyorsun matematik gibi, gerisini veriyorsun GHC diye, compiler yapıyor kendisi.
**38:29** Hatta hiçbir şey öğrenmemiş olurduk herhalde, yani daha doğrusu şöyle, undergrad'a başladığımızda önce functional dilleri öğrenseydik, çok da bir şey öğrenmiyor olurduk, matematik işlemi yaptırıyor olurduk bilgisayara sadece. Biz tabii imperative öğreniyoruz. Hep böyle olagelmiştir yani eskiden beri zaten, çok az yer vardır ilk functional'la başlayan. E zaten öğrenilmesi gerekiyor yani imperative dillerin de eninde sonunda öğrenilmesi gerektiği için, sonuçta artık matematik değil de programlamaya daha yakın bir şey yapalım gibi öğreniliyor herhalde.
**38:59** R dili örnek olarak, bilim insanları... Evet R dili biraz daha istatistik şeylerinde daha... özellikle istatistikçilerin çok kullandığı bir dil. Güzel tabii şey yani, o biraz daha Python'a sanki yakındı diye hatırlıyorum syntax olarak.
**39:26** Şimdi summary olarak: "Functional programming languages use function application, conditional expressions, recursion, and functional forms to control program execution." Böyle önemli kavramlar var. "Lisp began as a purely functional language and later included imperative features." Yani ister istemez işte yani, sadece fonksiyonel kalamıyor, Lisp bile imperative şeyler eklemek durumunda kalmış yani. Bazen inatçı şeyler oluyor, Haskell gibi "inatçı purely kalalım" filan diyen diller oluyor ama öyle yani.
**39:58** "Scheme is a relatively simple dialect of Lisp that uses static scoping exclusively." Static scope'a da birazdan başlayacağım 10:52 saat. Bir saatimiz geçti, hatta bir buçuk saat falan olmuş. Bir kısa bir ara verip diğer slayta geçeceğim.
**40:14** "Common Lisp is a large Lisp-based language." Lisp zaten, Lisp'in ana kolu gibi bir şey. Hani Debian'dan Ubuntu filan çıkıyor ama Debian duruyor ya filan, onun gibi bir şey yani Common Lisp. Lisp'in ana kolu.
**40:39** "ML is a static-scoped and strongly typed functional language that uses type inference." "Haskell is a lazy functional language supporting infinite lists and set comprehension."
**40:52** "F# is a .NET functional language that also supports imperative and object-oriented programming." "Some primarily imperative languages now incorporate some support for functional programming." Hepsinde var, Java'da filan da var. Java kaçta geldi, 18'de mi? Diğerden sonra onu da dahil ettiler Java'da da yapılıyor yani biliyorsunuz zaten. Hani böyle `->` işaretiyle filan yapılıyor yani fonksiyonel çağrılar yapabiliyorsunuz.
**41:22** "Purely functional languages have advantages over imperative alternatives, but still are not very widely used." Yani, very widely used değil. Bu dediğim gibi, projenin içinde belli kısımlarda kullanılan şeyler. Şimdi büyük projelere baktığımızda gençler, genelde şey oluyor, diyelim ki bir string operasyonları lazım olan bir yer var, mesela pattern matching yapılması gereken bir şey var. Orada ona en uygun dil ne, atıyorum Perl, o kısmı Perl'le yazıyorlar mesela. Veya bir kısım var, orada matematiksel bir şeyler yapılıyor, o kısmı diyelim ki açıyor adam Haskell'le yapıyor o kısmını. Ama programın geneli işte Python'la veya Java'yla veya C ile, Java Stream API, evet.
**42:12** Neyse, burada duralım. Bunu kapatayım ben, burada save olsun. Tamam. Bir 10 dakika falan bir ara verip diğer şeye geçeceğiz. Şimdi record'ı da durdurayım ben.
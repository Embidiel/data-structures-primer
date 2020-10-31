# Data Structures Primer


## Ano?
***Isang way / concept para i-organize o i-manage yung isa or maraming data (collection of data values) para mag-accomplish ng isang task / mag solve ng problem.***

Everyday di natin namamalayan, gumagamit tayo ng isang Data Structure. For example sa emails kapag binibisita natin yung GMail. May list of emails doon na naka organized kung spam ba or new yung email. That example uses a Data Structure under the hood para i-organize yung emails.

***Bawat isang type din ng Data Structure meron silang ineexpose na functionality to manipulate data like adding, moving or removing data.***

![enter image description here](https://i.ibb.co/7Qqnvqx/image.png)


## Complexity Analysis

Para magka better understanding tayo about sa Data Structures need natin alamin kung ano yung Complexity Analysis ng bawat type ng Data Structure.

Sa isang problem, pwedeng magkaroon ng maraming solution. Ngayon ang tanong equal ba yung bawat solution sa isang problem? The answer is no.  ***Yung isang solution pwedeng maging better sa isang solution.***
So para malaman kung ano yung better na solution, ginagamit natin yung Complexity Analysis.

Meron dalawang types ng Complexity. Time Complexity at Space Complexity. 
***Time Complexity measures how fast or slow an algorithm can be*** while yung ***Space Complexity naman measures how much memory does an algorithm takes.***

Ang isang algorithm pwedeng magkaroon ng fast time complexity while having a bad space complexity. So minsan may trade offs, depende nalang sa use case mo.

So bawat functionality sa bawat type ng Data Structure natin nag-te-take ng time and space to perform. ***Kaya pag merong business problem tayong ma e-encounter it's best na alam natin yung Data Structure na best fit for the problem.*** Kailangan alamin natin yung best fit using Complexity Analysis.

![ ](https://i.ibb.co/H45W5Kv/image.png)


## Memory

Lets tackle about Memory. Punta tayo sa pinakabasic, kapag gumagawa tayo ng program, nag-iinitialize tayo ng variable diba. For example,

    const foobar = 1;

Itong variable na to, napupunta sa memory. So how do we think of memory? ***Imagine mo nalang sila as a slots or boxes. Itong mga box na to ay limited lang ang bilang.***

![enter image description here](https://i.ibb.co/jHQc7LP/image.png)

So under the hood ng program natin, ano ba nangyayari sa variable na nilagyan natin ng laman. ***Mapupunta to sa isang memory slot or memory slots na free or not used.***

![enter image description here](https://i.ibb.co/SmwdgkP/image.png)

***Sa perspective ng computer, ano ba yung 1? It's just 1s and 0s. Simply called Bits. Pag nag ii-store tayo ng kahit ano sa computer naii-store siya as Bits. A single memory slot can hold 8 bits or simply called Byte.
Any piece of data can be transformed into 1s and 0s.***

![ ](https://i.imgur.com/zHeEvm4.png)

So wait, paano kung malaki yung data na kailangan natin i-store? Paano tayo makakapagstore ng larger value than 256? ***Kung nanggaling ka sa Java background siguro narinig mo na yung 32 bit at 64 bit integer. Ang type `int` ay isang 32 bit integer at ang type `long` ay isang  64 bit integer.***

Kung Java gamit mong language at nag declare ka ng int foobar = 1. **Ma-dedeclare siya as a 32 bit integer. 32 / 8 (number of bits na kaya i-hold ng isang memory slot) = 4. Four free  contiguous memory slots ang masasakop kapag nagdeclare ka ng variable na iyan.** 

![enter image description here](https://i.imgur.com/8WbnQ1l.png)

Paano naman kung walang contiguous memory slots na free. Basically maghahanap lang yung computer mo ng free memory slots na sunod sunod at doon niya ipapasok. Parang example sa baba sa slot 16. 

![enter image description here](https://i.imgur.com/07wafwr.png)

***Paano kung may array tayo or a list of numbers na need i-store?*** So ganun parin yung concept. Example we declared `int nums = [1,2,3]`,
maghahanap parin yung computer natin ng ***contiguous free memory slots*** to store yung mga numbers na yan.

![enter image description here](https://i.imgur.com/pSukWZG.png)

Pwede rin tayo mag store sa isang memory slot ng isang address ng isa pang memory slot. Tinatawag itong ***pointers***. Instead na i-store natin yung data sa memory slot na napili natin pwede nalang i-store natin yung address nung memory slot sa data na gusto natin.

![enter image description here](https://i.imgur.com/JK1JLhE.png)
 
Take note lang na, yung mga ganitong process sa memory, behind the scenes sa PC natin, napakabilis lang mangyari. ***Imagine mo nalang na may direct access yung computer natin sa bawat memory slots.***

---

## Big O Notation

![enter image description here](https://mattjmatthias.co/content/images/big-o-chart.png)

![enter image description here](https://adrianmejia.com/images/big-o-running-time-complexity.png)

Eto yung ginagamit na ***measurement para malaman natin kung gaano ba kabilis o kabagal ang isang algorithm at kung paano ba siya nag ii-scale.***

Lets say gusto nating maghanap sa isang mahabang listahan ng mga libro like 1 million  records ng book title. Well maraming algorithms para sa pagse-search ng isang item, diferent levels ng complexity, yung iba mas mabilis kumpara sa ibang algorithms.

Ngayon ang tanong kung paano natin ma memeasure yung performance at complexity ng mga to?

![enter image description here](https://introcs.cs.princeton.edu/java/41analysis/images/order-of-growth.png)

***Forms of Big O Notation:***

 - O (1)
 - O (log n)
 - O (n)
 - O (n log n)
 - O (n ^ 2)
 - O (2 ^ n)
 - O (n!)

---
### O (1) or Constant Time

Kapag constant time ***walang pake-alam yung algorithm mo kung gaano kalaki o karami yung laman nung data set mo. Execution time is the same.***

![enter image description here](https://i.imgur.com/iaj66LZ.png)

***Example nito yung pag direct access ng isang array element using its index.*** Yung execution time is constant sa parehas na pagtawag ng `logSecondNumber` using 2 different data sets ay parehas lang.

---

### O (log n) or Logarithmic Time

Sa isang O (log n) algorithm, **yung execution time niya ay directly proportional sa logarithm nung n or nung number of inputs mo.**

***Sa computer science or coding, laging base 2 or binary logarithm yung ginagamit natin sa isang logarithm function.***

***Example #1:***

![enter image description here](https://hackernoon.com/hn-images/1*2zmw8UA3Ju93DskOT2ja0A.png)

For example, meron tayong 16 array elements at gusto natin makuha yung number 3. ***Pinaka famous example ng isang log n algorithm ay Binary Search.***

***Yung middle element yung parang pointer or identifier natin kung ayun na ba yung hinahanap natin.***

First step mag start tayo sa middle element, which is 16. I-cut natin into half yung array, 16 / 2 = 8. 8th element is 16. 3 yung hanap natin so hindi pa.

Second step, cut ulit. 8 / 2 = 4. 4th element is 8, di parin.
Third step, cut 4 / 2 = 2. 2nd element is 3 na nasa middle pointer natin.

***Best case scenario ng Binary search is 0(1) ang worst case naman at O (log n).***

***Example #2***

![enter image description here](https://i.imgur.com/wPaYJ5a.png)

Simple logarithmic loop na base 2 ang gamit. N is 8. log(8) = 3 or
2 * 2 * 2 = 8.

---

### O (n) or Linear Time

Sinasabi dito na ***habang tumataas yung number of inputs mo ganun din yung bilang or execution time ng algorithm mo.***

For example, ***if every item na nasa listahan takes 10 seconds to load or mag pop up sa console.log ibig sabihin merong 40 seconds na execution time itong function mo.***

![enter image description here](https://i.imgur.com/Eao4jaN.png)


---

### O (n log n) or Linearithmic Time / Log-Linear Time 

Eto naman parang combination ng O(n) at O(log n) time complexity. ***Kaya naging n log n kasi n multiply by log n***. In math, sabihin na yung n natin is 8, our log n shall be 3 because `2 x 2 x 2 = 8`. Tapos 8 multiply by 3 = 24. ***Possible na 24 seconds yung execution time nung magiging algorithm natin.***

***Example #1***

Take as an example natin itong ***Merge Sort algorithm***.

![enter image description here](https://imgur.com/xJk7zEm.png)

Breakdown muna natin yung code sa taas. Sa loob ng `merge` na function, ***ilang beses dadaan yung while loop sa loob ng array? Hanggat may laman yung array, it means linear time or n.***

Punta naman tayo sa `mergeSort` na function, mapapansin natin dito is ***hinati niya yung 1 array into 2 separate arrays. Similar sa pattern ng binary search which is nag ce-create ng pivot or middle element.***

Tapos take note gumagamit siya ng recursion dito para ma accomplish yung, ***Logarithmic time or log n***.

---

### O (n ^ 2) or Quadratic Time

Dito naman ***yung execution time natin is directly proportional to the squared size of the input***. For example n natin is 2, 2 ^ 2 = 4 seconds,
4 ^ 2 = 16 seconds. ***Pinakabasic framework ng time complexity na to is a nested loop.***

![enter image description here](https://imgur.com/RAue6Yq.png)

---
### O (2 ^ n) or Exponential Time (Base 2)

It means that our execution time depends sa pa grow ng input natin in doubled. ***For example, our n is 4. 2 ^ 4 is 2 x 2 x 2 x 2 is 16.*** 

Example #1
Basic example neto is a fibonacci function.

![enter image description here](https://imgur.com/SrFiAa8.png)

## Arrays

![enter image description here](https://imgur.com/US1iSpE.png)

Pinaka basic or yung pinakastarting sa lahat ng Data Structures.
 Under the hood ano ba talaga ang nangyayari sa loob ng OS kapag nag handle tayo ng Array?

***Two types of array.***
- **Static**
- **Dynamic**

***Static array***, kung nagsimula ka sa Java or C++ background malamang nagamit mo na or narinig mo na tong term na to.
*Static is parang sinasabi natin sa computer natin na kailangan natin ng 3 free spaces para mag store ng 3 integers*

Example = `int arr[3]`

Gagawin ng computer ***maghahanap yan ng 3 free contiguous spaces to store yung 3 integers natin***. Assuming na
64 bit yung pag store per integer or 8 bytes. ***So 8x3 = 24. 24 Bytes free continuous space.***

***Lets talk about access naman, commonly ganito ginagawa natin [1] or access by index***. Under the hood pano ba yan
hina-handle ng computer natin?

Example = `console.log(arr[3]).`

***Sa ganyang scenario, alam na ng computer natin kung ano yung starting memory position kung saan siya nagsimula mag
declare ng integers sa memory slots***. Sa example sa picture, sa Memory Address 3 so kung isang integer mag take-up
ng 8 bytes.

3 - Memory address ng first integer
3 + 8 = 11, Memory address ng second integer
11 + 8 = 19,  Memory address ng third Integer

Ginagawa ng computer, ***given the index na gusto mong i-access tapos multiply by the bytes na tine-takeup ng isang
memory slot tapos add the memory address or position of the first element.***

8 - ***number of memory slots na tine-take ng isang integer***
2 - ***index ng array element na gusto natin makuha***
3 - ***starting memory address ng declared na array.***

8 x 2 = 16
16 + 3 = 19
`19` ***is the memory address of the value that we want to get***.

***Time Complexity*** : `0 (1)` Constant time.

![enter image description here](https://imgur.com/1NJCEEX.png)

***Dynamic Arrays*** naman, pag nag declare ng isang dynamic array meron palaging sobrang space so maganda to kapag gusto mo mag insert pa ng ibang elements.

Example gusto mo mag store ng 2 integers, ***sa dynamic array maglalaan pa ng extra space depende sa number of elements na dineclare mo***. For this example magiging 4.

Pag napuno naman yung dynamic array same procedure lang sa static array, ***just copy all the elements papunta sa free contiguous space na available sa memory tapos magdagdag ulit ng space depende sa number of elements.***

***Pagtapos ng copying, ifre-free up na yung previous memory slots na nagamit.***

Under the hood, ***Javascript & Python yung mga famous programming languages na gumagamit nito***.

## Linked List

![enter image description here](https://imgur.com/bo5eVxL.png)

***Almost similar sa Array.***

Ang key difference between sa **Array** at ***Linked List*** ay:

- Sa ***Array*** kailangan pag nag declare ka for example ng [1,2,3], kailangan sa loob ng memory canvas 
***meron dapat na 3 free contiguous memory slots (Sinabi ko lang na 3 for simplicity's sake lol).***

- Sa ***Linked List*** naman ***kahit hiwa-hiwalay yung pag store mo ng 3 different integers na yan.*** For example sa picture,
Si memory slot address 1 ay occupied na, pero si memory slot address 2 ay vacant tapos si memory slot 3 ay occupied.

***Pwedeng i-store mo nalang sa free addresses na 2 or so on. Basically kahit saan mo ipwesto basta free yung memory slot.***
***Tapos i-coconnect nalang yan*** using the concept of `pointers` (pointing to another memory's address).

Note lang ***yung memory addresses na `1,2,3` dito ay for simplicity lang***. ***In reality binary numbers yang addresses na yan.***

**Sa Linked Lists din may concept ng `nodes`**, so ***bawat value na i-dedeclare mo for example 3, Naka store yan sa isang node.***

Lets talk about the ***most common operations*** na ginagawa sa isang Linked List:

![enter image description here](https://imgur.com/1x6aqXy.png)

1.) ***Get***

Sa operation na get, ***different siya sa behavior ni Array kasi sa Array diba meron tayong concept ng index.***

Example : `arr[1] = 2.`

So basically ***instant yung pagkuha ng value, O(1) Constant Time***. 
Kasi ***kunin mo lang yung starting memory address
nung array*** tapos ***number of memory slots (assuming na 64 bit = 8 bytes) multiply by the given index, and then pag
add mo lang sa starting memory address*** and boom kuha mo na yung value na gusto mo.

***Note***: Check yung Array part nitong primer for example.

***Sa Linked List medyo complicated lang***, kasi para magretrieve ng value ang pinaka-reference mo ay yung head.
Tapos ***wala ka namang way to calculate the location nung gusto mong value na ma-retrieve e, kasi di sila dikit-dikit sa memory canvas pwedeng kalat kalat sila.***

So ***it will take O(n) or Linear Time starting from the head*** kung gusto mo mag get ng value.

 ***Best case O(1)*** kung nasa head yung value.

---

![enter image description here](https://imgur.com/U5fulaC.png)

2.) ***Insertion***

So kung sa ***behavior ng isang array kailangan natin mag shift ng elements by one position to the right***
kung gusto natin magpasok ng ***isang bagong element sa start ng array.***

Sa ***Linked List*** need lang natin ***mag create ng new node***. 
For example gusto natin ng 5 as a new value, ***gawa lang tayo ng
new node na laman ay 5 yung 5 na yun ayun na yung bagong head ng Linked List***. 

Tapos yung node na may value na 5, ***mag po-point sa old node or head na may value na 3.***

***Time complexity is O(1)*** kasi ***gumawa lang naman tayo ng bagong node at ginawa nating head, walang elements shifting 
na naganap.***

Paano naman kung gusto natin ***mag pasok ng new value sa gitna ng Linked List?*** 

Unfortunately, ***kailangan natin mag start sa head ng Linked List***.

 So sa example sa picture, lets start sa head node na may value na 5.

***From that node need natin daanan yung ibang nodes hanggang sa node na kung saan natin gustong mag insert ng value.***

Example lang gusto ko pagtapos ng node na may value na 1 magpasok. 

Head node w/ value 5 to node value 1. 
***After ng traversal na yan, mag insert na ako ng new node na may value na 6.*** 

Si node value 1 ***ang gagawin ko is ipo-point siya papunta sa new node value 6.***
Si new node value 6 naman, ***ipo-point ko siya sa previously pino-point ni node value 1, which is si node value 4.***

***Time complexity is O(n) or Linear Time*** for searching / traversal to kung saan natin gustong place magpasok sa Linked List.

***Pero yung mismong insertion is O(1) or Constant Time kasi we just need to point to another node.***

***Kung sa tail or end node naman.*** 

For example node value 2, ***si node value 2 nag po-point yan sa isang memory slot na may null value.*** 

So ***we just need to replace the null value with a new node na may value for example dito is 7.***

Insertion is ***generally depende sa implementation mo kung paano ka mag-insert ng value.***

***Yung ibang implementation ng Linked List may reference sa tail node.*** Tapos kung gusto mo mag insert sa tail or end node, ***just create a new node then point yung tail sa new node***.

 ***So it's just constant time or O(1).***

Pero ***kung wala kang reference or variable sa tail,*** ***pwedeng maging linear time kasi need mo mag start sa head.***

---

***Types of Linked List***

Merong ***3 types of Linked List***. 

Itong diniscuss ko dito ay isang ***Singly Linked List.***

Sa ***Singly Linked List meron lang isang pointer as you can see sa picture.*** 
Another node points to another node.
Kung sa code tinatawag tong `next` na property.

Second type is a ***Doubly Linked List***, enhanced version ni Singly Linked List. 

![Example of Doubly Linked List](https://imgur.com/9Uydd4C.png)

Meron kang ***2 pointers sa isang node***. The `previous` and `next` properties.

Si ***head naka point yung previous / prev pointer sa isang null value.***
Si ***tail naka point yung next pointer sa isang null value.***

Isa pang type is a ***Circular Linked List***. 

***Meron lang pointer si head node papunta sa tail***. 

***Tapos si tail naman meron ding pointer papunta sa head.***


---
## Hash Tables / Hash Map

Isa rin sa mga commonly used na Data Structures. 	

***It allows us to store values*** in a `key-value pair` format. 

***Every key may corresponding na value.***

Sa mga famous programming languages katulad ng Javascript at Python ay implemented na ito easily or built-in na.

***Javascript (Regular Object)*** 

***Example:*** `const dog = {nose: 1};`

***Python (Dictionary)***

***Example:*** `dog = {nose : 1};`

Pwede rin natin itong i-tulad sa array kasi sa array may concept ng index for lookups. 

Counterpart niya sa Hash Map ay isang `key`. 
***So O(1) din ang pag get ng value nito.***

Under the hood medyo complicated ang pag gawa nito.
Ang isang Hash Table ay ***built on top of arrays.*** 

***Every key na pinapasok natin sa isang hash table ay
napupunta sa isang*** `Hash function`.

***Basically yung isang hash function ay kino-convert niya yung isang key which is a string, into an integer.***

Tapos ***yung integer na to ay yung nagiging index sa array*** kung saan natin ilalapag yung value na partnered doon sa isang key.

![enter image description here](https://imgur.com/23GQLa5.png)

Check example image above.

***So is it possible ba na yung isang key tapos another key magkaroon ng same integer result pagkadaan sa isang hash function?***

Yes possible. Ang tawag diyan ay isang `collision`.

Sa ganyang setup ***bawat isang slot sa array ay mag po-point sa isang Linked List.***

Ibig sabihin nito ***average scenario na yung O(1)*** ***or Constant time for get / lookup.***

![enter image description here](https://imgur.com/YrQ7tGq.png)

Pero ***ang worst case is kapag nagkaroon ng multiple collisions*** ito ay ***magiging O(n) or Linear Time.***


***Paano naman kapag ang dami mo ng keys na initialize pero limited pala yung length nung array?***

***Pwede nating gamitin yung concept ng Dynamic Arrays*** at magkaroon ng `resizing`.

Parang yung flow is ***every time na nasa limit na yung array or puno na*** ***just copy lahat ng laman ng array na yun which are mga linked lists.***

![enter image description here](https://imgur.com/Zz1Skhk.png)

***Tapos ipasok siya sa new array na doubled in size***. 

***Tapos every key ulit na declared sa Hash Map ay papasok
ulit sa*** `hash function` and ***then every values mama-map na sa corresponding index sa new array.***

Kasi kapag di natin ginawa tong resizing ***it's very possible na lumaki lang yung mga linked list natin at magkaroon ng multiple collisions.***

Regarding hash functions marami ng magagaling na programmer na nag implement ng hash function katulad sa Javascript 
so medyo di na natin kailangan problemahin yan. 

Important lang na nalaman natin.

## Stacks & Queues

Itong dalawang data structures na to ay easy to grasp or understand even implementation ay madali rin.

Ang ***Stack*** ay ***isang LIFO or Last In First Out na Data Structure.***
Ibig sabihin kung sinong huling pumasok, siya yung unang makakalabas.

Real world example ay ***stack ng books, kung sinong nasa itaas yun yung kukunin natin.***

Sa ***Queue*** naman ay ***FIFO or First In First Out***. ***Kung sinong unang pumasok siya ang unang makakalabas.***

Real world example ay ***pagpila sa sinehan. Kung sinong unang makabili sa cashier ng ticket siya yung unang makakalabas sa pila.***

May kaibahan ng implementation si Stack at Queue.

Si ***Stack ay implemented gamit ang Arrays.*** 
Si ***Queue naman ay built on top of Linked List.***

So bakit ganito ang way ng pagbuo sa kanila?

Since ***Stack*** is a Last In First Out type, ***mas convenient in terms of time kung Array ang gagamitin since sa last element lang naman tayo nagtatanggal ng item (`pop`).***

Compared sa ***Queue*** na ***sa unahan tayo nagtatanggal ng item (`dequeue`).*** ***Kung Array ang gagamitin sa Queue kailangan pa natin i-shift yung bawat items sa array papunta sa kaliwa kung saan natanggal yung first element.***  Which takes O(n) time.

Kung ***Linked List implementation pwedeng direkta na natin tanggalin yung head tapos ipalit natin yung next na node na naka point sa previous na head.*** . Eto O (1) time lang.



![enter image description here](https://imgur.com/eJcdzEN.png)




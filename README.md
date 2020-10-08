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

Paano kung may array tayo or a list of numbers na need i-store? So ganun parin yung concept. Example we declared int nums = [1,2,3],
maghahanap parin yung computer natin ng contiguous free memory slots to store yung mga numbers na yan.

![enter image description here](https://i.imgur.com/pSukWZG.png)

20:52

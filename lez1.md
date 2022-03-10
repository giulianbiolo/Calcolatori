<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML">
</script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$','$'], ['\\(','\\)']],
      processEscapes: true},
      jax: ["input/TeX","input/MathML","input/AsciiMath","output/CommonHTML"],
      extensions: ["tex2jax.js","mml2jax.js","asciimath2jax.js","MathMenu.js","MathZoom.js","AssistiveMML.js", "[Contrib]/a11y/accessibility-menu.js"],
      TeX: {
      extensions: ["AMSmath.js","AMSsymbols.js","noErrors.js","noUndefined.js"],
      equationNumbers: {
      autoNumber: "AMS"
      }
    }
  });
</script>

Calcolatori - Lezione 2
=======================

Un computer è un'insieme di circuiti elettronici, in ogni circuito la corrente può passare o meno.  
Definiamo quindi noi una codifica tale per cui:  
- Passa Corrente: $1$  
- Non Passa Corrente: $0$  

Un computer memorizza e manipola sequenze di $0$ e $1$.  
Una singola cifra $0$ o $1$ è detta ***'bit'***.  
Una sequenza di $8$ bit è detta ***'byte'***.  
Una sequenza di $16$ bit è detta ***'word'***.  
Una sequenza di $32$ bit è detta ***'dword'***.  
Una sequenza di $64$ bit è detta ***'qword'***.  

---
I Numeri Naturali:
------------------

### Rappresentazione:  

La codifica di numeri naturali è abbastanza banale,
infatti nel sistema decimale si sfrutta già una codifica di questo tipo, dobbiamo solo spostarci nel mondo binario.  
$$501_{10} = 5*100 + 0*10 + 1*1$$  
$$501_{10} = 5*10^2 + 0*10^1 + 1*10^0$$  
Per cui possiamo tradurre questa codifica utilizzando esponenziazioni di $2$ invece che $10$.  
Facciamo alcuni esempi:  
$$1101_2 = 1∗2_3 + 1∗2_2 + 0∗2_1 + 1∗2_0 = 13_{10}$$
$$170_8 = 1*8^2 + 7*8^1 + 0*8^0 = 120_{10}$$
Ogni byte quindi può assumere $2^8 = 256$ valori.  
Per convertire da $B \rightarrow 10$ ci basta fare la somma dei valori $c_i\cdot B^i$.  
Per convertire da $10 \rightarrow B$ ci basta dividere iterativamente il numero per $B$ ed i resti si *"impilano"* a sinistra nel numero convertito, e ad x si assegna il quoziente.  
Esempio:  
$$1000_{10}=?_2$$
|X|X/2|X%2|
|:--:|:--:|:--:|
|1000|500|0|
|500|250|0|
|250|125|0|
|125|62|1|
|62|31|0|
|31|15|1|
|15|7|1|
|7|3|1|
|3|1|1|
|1|0|1|
$$1000_{10}=1111101000_2$$
$$1000_{10}=?_{16}$$
|X|X/16|X%16|
|:--:|:--:|:--:|
|1000|62|8|
|62|3|14(E)|
|3|0|3|
$$1000_{10}=3E8_{16}$$  

Un aspetto peculiare dei calcolatori, oltre al fatto che utilizzano un'aritmetica binaria invece che decimale, è che possono allocare al massimo una certa quantità di memoria, ossia bit, cifre, ad ogni numero.  
Per cui allocati $n$ bit si possono esprimere al massimo $2^n - 1$ numeri.  
Se un numero eccede i limiti della rappresentazione, quello che osserveremo sugli $n$ bit sarà il numero stesso modulo $2^n$.  

### Operazioni:



---
I Numeri Reali:
---------------
I Floating Point non vengono rappresentati in complemento a $2$ in C, ma si usa 
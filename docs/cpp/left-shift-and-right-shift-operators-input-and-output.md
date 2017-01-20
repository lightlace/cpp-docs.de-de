---
title: "Leftshift- und Rightshift-Operatoren (&gt;&gt; und &lt;&lt;)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "<<"
  - ">>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<<-Operator, Mit spezifischen Objekten"
  - ">>-Operator"
  - "Bitweise Schiebeoperatoren"
  - "left shift-Operatoren"
  - "Operatoren [C++], Schiebeoperatoren"
  - "Rechtsschiebeoperatoren"
  - "Schiebeoperatoren"
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# Leftshift- und Rightshift-Operatoren (&gt;&gt; und &lt;&lt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zu den bitweisen Schiebeoperatoren zählt der Right Shift\-Operator \(`>>`\), der die Bits von `shift_expression` nach rechts verschiebt, und der Left Shift\-Operator \(`<<`\), der die Bits von `shift_expression` nach links verschiebt.  <sup>1</sup>  
  
## Syntax  
  
```  
  
        shift-expression << additive-expression  
shift-expression >> additive-expression  
```  
  
## Hinweise  
  
> [!IMPORTANT]
>  Die folgenden Beschreibungen und Beispiele gelten bei Windows für x86\- und x64\-Architekturen.  Die Implementierung von Left Shift\-Operatoren und Right Shift\-Operatoren unterscheidet sich bei Windows RT für ARM\-Geräte deutlich.  Weitere Informationen finden Sie im Abschnitt „Shift Operators“ des Blogbeitrags [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx).  
  
## Verschiebungen nach links  
 Der Left Shift\-Operator bewirkt, dass die Bits in `shift-expression` um die Anzahl von Positionen nach links verschoben werden, wie es durch den `additive-expression` angegeben wird.  Die durch den Verschiebevorgang frei gewordenen Bitpositionen werden mit Nullen angefüllt.  Eine Verschiebung nach links ist eine logische Verschiebung \(die Bits, die über das Ende hinaus verschoben werden, werden verworfen, einschließlich des Vorzeichenbits\).  Weitere Informationen über die Arten von bitweisen Verschiebungen finden Sie unter [Bitwise shifts](http://en.wikipedia.org/wiki/Bitwise_shift).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Verschiebevorgänge nach links nicht signierte Zahlen verwenden.  Das folgende Beispiel veranschaulicht, was mit den Bits geschieht, indem der Wert als ein Bitset dargestellt wird.  Weitere Informationen finden Sie unter [bitset\-Klasse](../standard-library/bitset-class.md).  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short1 = 4;      
    bitset<16> bitset1{short1};   // the bitset representation of 4  
    cout << bitset1 << endl;  // 0000000000000100  
  
    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;  // 0000000000001000  
  
    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16  
    bitset<16> bitset3{short3};  
    cout << bitset3 << endl;  // 0000000000010000  
}  
  
```  
  
 Wenn Sie eine signierte Zahl nach links verschieben, sodass das Vorzeichenbit davon betroffen ist, ist das Ergebnis nicht definiert.  Das folgende Beispiel veranschaulicht, was in Visual C\+\+ geschieht, wenn ein 1\-Bit nach links in die Vorzeichenbitposition verschoben wird.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 16384;      
    bitset<16> bitset1{short2};  
    cout << bitset1 << endl;  // 0100000000000000   
  
    short short3 = short1 << 1;  
    bitset<16> bitset3{short3};  // 16384 left-shifted by 1 = -32768  
    cout << bitset3 << endl;  // 100000000000000  
  
    short short4 = short1 << 14;  
    bitset<16> bitset4{short4};  // 4 left-shifted by 14 = 0  
    cout << bitset4 << endl;  // 000000000000000    
}  
```  
  
## Verschiebungen nach rechts  
 Der Right Shift\-Operator bewirkt, dass das Bitmuster in `shift-expression` um die Anzahl von Positionen nach rechts verschoben wird, wie es durch den `additive-expression` angegeben wird.  Für unsignierte Zahlen werden die durch den Verschiebevorgang frei gewordenen Bitpositionen mit Nullen angefüllt.  Für signierte Zahlen wird das Vorzeichenbit verwendet, um die frei gewordenen Bitpositionen zu füllen.  In anderen Worten, wenn die Zahl positiv ist, wird 0 verwendet, und wenn die Zahl negativ ist, wird 1 verwendet.  
  
> [!IMPORTANT]
>  Das Ergebnis der Verschiebung einer signierten negativen Zahl nach rechts ist implementierungsabhängig.  Obwohl Visual C\+\+ das Vorzeichenbit verwendet, um frei gewordene Bitpositionen zu füllen, gibt es keine Garantie, dass auch andere Implementierungen dies tun werden.  
  
 Dieses Beispiel veranschaulicht, wie Verschiebevorgänge nach rechts nicht signierte Zahlen verwenden:  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short11 = 1024;  
    bitset<16> bitset11{short11};  
    cout << bitset11 << endl;     // 0000010000000000  
  
    unsigned short short12 = short11 >> 1;  // 512  
    bitset<16> bitset12{short12};  
    cout << bitset12 << endl;     // 0000001000000000  
  
    unsigned short short13 = short11 >> 10;  // 1  
    bitset<16> bitset13{short13};  
    cout << bitset13 << endl;     // 0000000000000001  
  
    unsigned short short14 = short11 >> 11;  // 0  
    bitset<16> bitset14{short14};  
    cout << bitset14 << endl;     // 0000000000000000}  
}  
```  
  
 Das nächste Beispiel zeigt Verschiebevorgänge nach rechts mit positiven, signierten Zahlen.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 1024;  
    bitset<16> bitset1{short1};  
    cout << bitset1 << endl;     // 0000010000000000  
  
    short short2 = short1 >> 1;  // 512  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;     // 0000001000000000  
  
    short short3 = short1 >> 11;  // 0  
    bitset<16> bitset3{short3};     
    cout << bitset3 << endl;     // 0000000000000000  
}  
```  
  
 Das nächste Beispiel zeigt Verschiebevorgänge nach rechts mit negativen, signierten Ganzzahlen.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short neg1 = -16;  
    bitset<16> bn1{neg1};  
    cout << bn1 << endl;  // 1111111111110000  
  
    short neg2 = neg1 >> 1; // -8  
    bitset<16> bn2{neg2};  
    cout << bn2 << endl;  // 1111111111111000  
  
    short neg3 = neg1 >> 2; // -4  
    bitset<16> bn3{neg3};  
    cout << bn3 << endl;  // 1111111111111100  
  
    short neg4 = neg1 >> 4; // -1  
    bitset<16> bn4{neg4};      
    cout << bn4 << endl;  // 1111111111111111  
  
    short neg5 = neg1 >> 5; // -1   
    bitset<16> bn5{neg5};      
    cout << bn5 << endl;  // 1111111111111111  
}  
```  
  
## Verschiebungen und Heraufstufungen  
 Die Ausdrücke auf beiden Seiten eines Schiebeoperators müssen vom Typ „Ganzzahl“ sein.  Ganzzahlerweiterungen werden nach den in [Ganzzahlige Erweiterungen](../misc/integral-promotions.md) beschriebenen Regeln ausgeführt.  Der Typ des Ergebnisses ist der gleiche, wie der Typ des heraufgestuften `shift-expression`.  
  
 Im folgenden Beispiel wird eine Variable vom Typ `char` zu einem `int` heraufgestuft.  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;  // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;   // int  
}  
```  
  
## Weitere Details  
 Das Ergebnis eines Verschiebevorgangs ist nicht definiert, wenn `additive-expression` negativ ist oder wenn `additive-expression` größer oder gleich der Anzahl von Bits im \(heraufgestuften\) `shift-expression` ist.  Kein Verschiebungsvorgang wird ausgeführt, wenn `additive-expression` 0 ist.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned int int1 = 4;  
    bitset<32> b1{int1};  
    cout << b1 << endl;    // 00000000000000000000000000000100  
  
    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior  
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior  
  
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int6 = int1 << 0;  
    bitset<32> b6{int6};  
    cout << b6 << endl;    // 00000000000000000000000000000100 (no change)}  
}  
```  
  
## Fußnoten  
 1 Folgendes ist die Beschreibung des Schiebeoperators in der C\+\+ ISO\-Spezifikation \(INCITS\/ISO\/IEC 14882\-2011\[2012\]\), Abschnitte 5.8.2 und 5.8.3.  
  
 Der Wert von `E1 << E2` ist `E1` nach links verschobene `E2`\-Bitpositionen; frei gewordene Bitpositionen werden mit Nullen angefüllt.  Wenn `E1` einen nicht signierten Typ hat, ist der Wert des Ergebnisses `E1 × 2`<sup>E2</sup>, wobei das reduzierte Modulo eins mehr als der maximale Wert, der im Ergebnistyp dargestellt werden kann.  Anderenfalls, wenn `E1` einen signierten Typ und einen nicht negativen Wert hat, und `E1 × 2`<sup>E2</sup> im entsprechenden nicht signierten Typ des Ergebnistyps dargestellt werden kann, dann ist der Wert, der in den Ergebnistyp konvertiert wird, der Ergebniswert; anderenfalls ist das Verhalten nicht definiert.  
  
 Der Wert von `E1 >> E2` ist `E1` nach rechts verschobene `E2`\-Bitpositionen.  Wenn `E1` einen nicht signierten Typ hat oder wenn `E1` einen signierten Typ und einen nicht negativen Wert hat, ist der Wert des Ergebnisses der integrale Teil des Quotients von `E1/2`<sup>E2</sup>.  Wenn `E1` einen signierten Typ und einen negativen Wert hat, ist der Ergebniswert durch die Implementierung definiert.  
  
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
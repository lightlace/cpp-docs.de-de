---
title: "align (C++)"
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
  - "align"
  - "align_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], align"
  - "align __declspec-Schlüsselwort"
ms.assetid: 9cb63f58-658b-4425-ac47-af8eabfc5878
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# align (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie in Visual Studio 2015 und höher den C\+\+11\-Standard\-`alignas`\-Spezifizierer, um die Ausrichtung zu bestimmen.  Weitere Informationen finden Sie unter [Ausrichtung](../cpp/alignment-cpp-declarations.md).  
  
 **Microsoft\-spezifisch**  
  
 Verwenden Sie `__declspec(align(#))`, um die Ausrichtung von benutzerdefinierten Daten genau zu steuern \(z. B. statische Speicherbelegungen oder automatische Daten in einer Funktion.\)  
  
## Syntax  
  
```  
__declspec( align( # ) ) declarator  
```  
  
## Hinweise  
 Das Schreiben von Anwendungen, die die neuesten Prozessoranweisungen verwenden, bringt mehrere neue Einschränkungen und Probleme mit sich.  Insbesondere machen viele neue Anweisungen die Ausrichtung von Daten an 16\-Byte\-Grenzen erforderlich.  Darüber hinaus verbessern Sie durch die Ausrichtung häufig verwendeter Daten an der Cachezeilengröße eines bestimmten Prozessors die Cacheleistung.  Wenn Sie beispielsweise eine Struktur definieren, deren Größe kleiner ist als 32 Bytes, sollten Sie sie an 32 Bytes ausrichten, um sicherzustellen, dass Objekte dieses Strukturtyps effizient zwischengespeichert werden.  
  
 \# ist der Ausrichtungswert.  Gültige Einträge sind ganzzahlige Potenzen von zwei von 1 bis 8192 \(Bytes\), z. B. 2, 4, 8, 16, 32 oder 64.  `declarator` sind die Daten, die Sie als ausgerichtet deklarieren.  
  
 Unter `size_t`\_\_alignof erfahren Sie, wie Sie einen Wert vom Typ [zurückgeben können, der der Ausrichtungsanforderung des Typs entspricht.](../cpp/alignof-operator.md) Unter [\_\_unaligned](../cpp/unaligned.md) finden Sie Informationen dazu, wie nicht ausgerichtete Zeiger deklariert werden, wenn 64\-Bit\-Prozessoren verwendet werden.  
  
 Sie können `__declspec(align(#))` verwenden, wenn Sie eine `struct`, `union` oder `class` definieren oder wenn Sie eine Variable deklarieren.  
  
 Der Compiler gewährleistet oder versucht nicht, das Ausrichtungsattribut der Daten während des Kopierens oder Umwandeln von Daten beizubehalten.  Beispielsweise kann [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) eine mit `__declspec(align(#))` deklarierte Struktur an eine beliebige Position kopieren.  Beachten Sie, dass normale Zuweisungen, wie [malloc](../c-runtime-library/reference/malloc.md), C\+\+\-[operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) und die Win32\-Zuweisungen, Arbeitsspeicher zurückgeben, der höchstwahrscheinlich nicht ausreichend für `__declspec(align(#))`\-Strukturen oder Strukturarrays ausgerichtet ist.  Um sicherzustellen, dass das Ziel des Kopiervorgangs oder der Datenumwandlung richtig ausgerichtet ist, verwenden Sie [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md), oder schreiben Sie eine eigene Zuweisung.  
  
 Die Ausrichtung für Funktionsparameter können Sie nicht angeben.  Wenn die Daten, die über ein Ausrichtungsattribut verfügen, als Wert auf dem Stapel übergeben werden, wird die Ausrichtung durch die Aufrufkonvention gesteuert.  Falls die Datenausrichtung in der aufgerufenen Funktion wichtig ist, kopieren Sie vor der Verwendung den Parameter in den korrekt ausgerichteten Speicher.  
  
 Ohne `__declspec(align(#))` richtet Visual C\+\+ im Allgemeinen die Daten an natürlichen Begrenzungen entsprechend dem Zielprozessor und der Datengröße aus, bis zu 4\-Byte\-Begrenzungen auf 32\-Bit\-Prozessoren und 8\-Byte\-Begrenzungen auf 64\-Bit\-Prozessoren.  Daten in Klassen oder Strukturen werden in der Klasse oder Struktur am Minimum ihrer natürlichen Ausrichtung und der aktuellen Verpackungseinstellung ausgerichtet \(von \#Pragma `pack` oder der **\/Zp**\-Compileroption\).  
  
 In diesem Beispiel wird die Verwendung von `__declspec(align(#))` veranschaulicht:  
  
```  
__declspec(align(32)) struct Str1{  
   int a, b, c, d, e;  
};  
```  
  
 Dieser Typ verfügt nun über ein 32\-Byte\-Ausrichtungsattribut.  Dies bedeutet, dass alle statischen und automatischen Instanzen auf einer 32\-Byte\-Begrenzung beginnen.  Zusätzliche Strukturtypen, die mit diesem Typ als Member deklariert werden, behalten die Ausrichtungsattribute dieses Typs bei, d. h. jede Struktur mit `Str1` als Element weist ein Ausrichtungsattribut von mindestens 32 auf.  
  
 Beachten Sie, dass `sizeof(struct Str1)` gleich 32 ist.  Wenn ein Array von Str1\-Objekten erstellt wird und die Basis des Arrays mit 32 Bytes ausgerichtet ist, ist demnach jeder Member des Arrays auch mit 32 Bytes ausgerichtet.  Um ein Array mit einer im dynamischen Speicher korrekt ausgerichteten Basis zu erstellen, verwenden Sie [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md), oder schreiben Sie eine eigene Zuweisung.  
  
 Der `sizeof`\-Wert für jede Struktur ist der Offset des letzten Members plus die Größe dieses Members, aufgerundet auf das nächste Vielfache des größten Memberausrichtungswerts oder den Ausrichtungswert der gesamten Struktur, je nachdem, welcher Wert größer ist.  
  
 Für die Strukturausrichtung verwendet der Compiler diese Regeln:  
  
-   Sofern sie nicht mit `__declspec(align(#))` überschrieben wird, ist die Ausrichtung eines skalaren Strukturmembers das Minimum seiner Größe und der aktuellen Verpackung.  
  
-   Sofern sie nicht mit `__declspec(align(#))` überschrieben wird, ist die Ausrichtung einer Struktur das Maximum der einzelnen Ausrichtungen ihrer Member.  
  
-   Ein Strukturmember wird bei einem Offset vom Anfang seiner übergeordneten Struktur platziert, die das kleinste Vielfache seiner Ausrichtung größer oder gleich dem Offset des Endes des vorhergehenden Members ist.  
  
-   Die Größe einer Struktur ist das kleinste Vielfache seiner Ausrichtung größer oder gleich dem Offset des Endes des letzten Members.  
  
 `__declspec(align(#))` kann lediglich Ausrichtungseinschränkungen erhöhen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Ausrichtungsbeispiele](#vclrfalignexamples)  
  
-   [Definieren neuer Typen mit \_\_declspec \(align \(\#\)\)](#vclrf_declspecaligntypedef)  
  
-   [Ausrichten von Daten im lokalen Threadspeicher](#vclrfthreadlocalstorageallocation)  
  
-   [Funktionsweise der Ausrichtung mit der Verpackung von Daten](#vclrfhowalignworkswithdatapacking)  
  
-   [Beispiele für die Strukturausrichtung](../build/examples-of-structure-alignment.md) \(x64\-spezifisch\)  
  
##  <a name="vclrfalignexamples"></a> Ausrichtungsbeispiele  
 Die folgenden Beispiele zeigen, wie sich `__declspec(align(#))` auf die Größe und die Ausrichtung der Datenstrukturen auswirkt.  Die Beispiele gehen von folgenden Definitionen aus:  
  
```  
#define CACHE_LINE  32  
#define CACHE_ALIGN __declspec(align(CACHE_LINE))  
```  
  
 In diesem Beispiel wird die `S1`\-Struktur mit `__declspec(align(32))` definiert.  Alle Verwendungen von `S1` für eine Variablendefinition oder andere Typdeklarationen sind mit 32 Bytes ausgerichtet.  `sizeof(struct S1)` gibt 32 zurück, und `S1` weist 16 Auffüll\-Bytes auf, die den 16 Bytes folgen, die für die Aufnahme der vier ganzen Zahlen erforderlich sind.  Jeder `int`\-Member erfordert die 4\-Byte\-Ausrichtung, aber die Ausrichtung der Struktur selbst wird als 32 deklariert.  Daher ist die Gesamtausrichtung 32.  
  
```  
struct CACHE_ALIGN S1 { // cache align all instances of S1  
   int a, b, c, d;  
};  
struct S1 s1;   // s1 is 32-byte cache aligned  
```  
  
 In diesem Beispiel gibt `sizeof(struct S2)` 16 zurück, was genau der Summe der Membergrößen entspricht, da es ein Vielfaches der größten Ausrichtungsanforderung \(ein Vielfaches von 8\) ist.  
  
```  
__declspec(align(8)) struct S2 {  
   int a, b, c, d;  
};  
```  
  
 Im folgenden Beispiel gibt `sizeof(struct S3)` 64 zurück.  
  
```  
struct S3 {  
   struct S1 s1;   // S3 inherits cache alignment requirement  
                  // from S1 declaration  
   int a;         // a is now cache aligned because of s1  
                  // 28 bytes of trailing padding  
};  
```  
  
 Beachten Sie in diesem Beispiel, dass `a` die Ausrichtung des natürlichen Typs, in diesem Fall 4 Bytes, aufweist.  Allerdings muss `S1` mit 32 Bytes ausgerichtet sein.  28 Auffüll\-Bytes folgen `a`, sodass `s1` am Offset 32 beginnt.  `S4` erbt dann die Ausrichtungsanforderung von `S1`, da es die größte Anforderungsausrichtung in der Struktur ist.  `sizeof(struct S4)` gibt 64 zurück.  
  
```  
struct S4 {  
   int a;  
   // 28 bytes padding  
    struct S1 s1;      // S4 inherits cache alignment requirement of S1  
};  
```  
  
 Die folgenden drei Variablendeklarationen verwenden auch `__declspec(align(#))`.  In jedem Fall muss die Variable mit 32 Bytes ausgerichtet sein.  Im Fall des Arrays ist die Basisadresse des Arrays, nicht jeder Arraymember, mit 32 Bytes ausgerichtet.  Der `sizeof`\-Wert für jeden Arraymember wird nicht von der Verwendung von `__declspec(align(#))` beeinflusst.  
  
```  
CACHE_ALIGN int i;  
CACHE_ALIGN int array[128];  
CACHE_ALIGN struct s2 s;  
```  
  
 Um jeden Member eines Arrays auszurichten, sollte Code wie dieser verwendet werden:  
  
```  
typedef CACHE_ALIGN struct { int a; } S5;  
S5 array[10];  
```  
  
 In diesem Beispiel sehen Sie, dass die Ausrichtung der Struktur selbst und die Ausrichtung des ersten Elements identisch sind:  
  
```  
CACHE_ALIGN struct S6 {  
   int a;  
   int b;  
};  
  
struct S7 {  
   CACHE_ALIGN int a;  
               int b;  
};  
```  
  
 `S6` und `S7` weisen identische Ausrichtungs\-, Speicherbelegungs\- und Größeneigenschaften auf.  
  
 In diesem Beispiel ist die Ausrichtung der Startadressen von a, b, c und d jeweils 4, 1, 4 und 1.  
  
```  
void fn() {   
   int a;  
   char b;  
   long c;  
   char d[10]  
}   
```  
  
 Wenn der Speicher für Heaps zugewiesen wird, hängt die Ausrichtung davon ab, welche Speicherbelegungsfunktion aufgerufen wird.  Wenn Sie beispielsweise `malloc` verwenden, hängt das Ergebnis von der Größe des Operanden ab.  Wenn *arg* \>\= 8, wird der zurückgegebene Arbeitsspeicher mit 8 Bytes ausgerichtet.  Wenn *arg* \< 8 ist, ist die Ausrichtung des zurückgegebenen Arbeitsspeichers die erste Potenz von 2 weniger als *arg*.  Wenn Sie beispielsweise "malloc\(7\)" verwenden, ist die Ausrichtung 4 Bytes.  
  
##  <a name="vclrf_declspecaligntypedef"></a> Definieren neuer Typen mit \_\_declspec \(align \(\#\)\)  
 Sie können einen Typ mit einem Ausrichtungsmerkmal definieren.  
  
 Beispielsweise können Sie eine `struct`  folgendermaßen mit einem Ausrichtungswert definieren:  
  
```  
struct aType {int a; int b;};  
typedef __declspec(align(32)) struct aType bType;  
```  
  
 Jetzt haben `aType` und `bType` dieselbe Größe \(8 Bytes\), aber Variablen vom Typ `bType` werden mit 32 Bytes ausgerichtet sein.  
  
##  <a name="vclrfthreadlocalstorageallocation"></a> Ausrichten von Daten im lokalen Threadspeicher  
 Statische lokale Threadspeicher \(TLS\), die mit dem `__declspec(thread)`\-Attribut erstellt und im TLS\-Abschnitt des Images platziert wurden, verhalten sich bei der Ausrichtung wie normale statische Daten.  Zum Erstellen von TLS\-Daten ordnet das Betriebssystem die Größe des TLS\-Abschnitts zu und berücksichtigt das Ausrichtungsattribut für TLS\-Abschnitte.  
  
 Dieses Beispiel zeigt verschiedene Möglichkeiten, ausgerichtete Daten in den lokalen Threadspeicher zu platzieren.  
  
```  
// put an aligned integer in TLS  
__declspec(thread) __declspec(align(32)) int a;     
  
// define an aligned structure and put a variable of the struct type  
// into TLS  
__declspec(thread) __declspec(align(32)) struct F1 { int a; int b; } a;  
  
// create an aligned structure   
struct CACHE_ALIGN S9 {  
   int a;  
   int b;  
};  
// put a variable of the structure type into TLS  
__declspec(thread) struct S9 a;  
```  
  
##  <a name="vclrfhowalignworkswithdatapacking"></a> Funktionsweise der Ausrichtung mit der Verpackung von Daten  
 Die **\/Zp**\-Compileroption und das `pack`\-Pragma wirken sich auf das Verpacken von Daten für Struktur\- und Unionmember aus.  Dieses Beispiel zeigt, wie **\/Zp** und `__declspec(align(#))` zusammenarbeiten:  
  
```  
struct S {  
   char a;  
   short b;  
   double c;  
   CACHE_ALIGN double d;  
   char e;  
   double f;  
};  
```  
  
 Die folgende Tabelle zeigt den Offset eines jeden Members mit einer Vielzahl von **\/Zp** \(oder \#pragma `pack`\)\-Werten, wobei gezeigt wird, wie die beiden interagieren.  
  
|Variable|\/Zp1|\/Zp2|\/Zp4|\/Zp8|  
|--------------|-----------|-----------|-----------|-----------|  
|a|0|0|0|0|  
|b|1|2|2|2|  
|c|3|4|4|8|  
|d|32|32|32|32|  
|e|40|40|40|40|  
|f|41|42|44|48|  
|sizeof\(S\)|64|64|64|64|  
  
 Weitere Informationen finden Sie unter [\/Zp \(Ausrichten des Strukturmembers\)](../build/reference/zp-struct-member-alignment.md).  
  
 Der Offset eines Objekts basiert auf dem Offset des vorherigen Objekts und der aktuellen Verpackungseinstellung, es sei denn, das Objekt weist ein `__declspec(align(#))`\-Attribut auf. In diesem Fall basiert die Ausrichtung auf dem Offset des vorherigen Objekts und dem `__declspec(align(#))`\-Wert für das Objekt.  
  
### Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [Übersicht über ARM\-ABI\-Konventionen](../build/overview-of-arm-abi-conventions.md)   
 [Übersicht über x64\-Aufrufkonventionen](../build/overview-of-x64-calling-conventions.md)
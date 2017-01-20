---
title: "pin_ptr (C++/CLI)"
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
  - "pin_ptr_cpp"
  - "stdcli::language::pin_ptr"
  - "pin_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pinning pointers"
  - "pin_ptr keyword [C++]"
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: 28
caps.handback.revision: "26"
ms.author: "mblome"
manager: "ghogen"
---
# pin_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert einen *festen Zeiger*, der nur mit der Common Language Runtime.  
  
## Alle Laufzeiten  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
## Windows\-Runtime  
 \(Diese Sprachfunktion wird nicht in Windows Runtime unterstützt.\)  
  
## Common Language Runtime  
 Ein *fester Zeiger* ist ein innerer Zeiger, der das Objekt verhindert, das dazu dem auf dem Heap der Garbage Collection dargestellt wird.  Das bedeutet, dass der Wert eines festen Zeigers von der Common Language Runtime nicht geändert.  Dies ist erforderlich, wenn Sie die Adresse einer verwalteten Klasse an eine nicht verwaltete Funktion übergeben, sodass die Adresse unerwartet nicht bei der Auflösung von nicht verwaltetem Funktionsaufrufs ändert.  
  
### Syntax  
  
```cpp  
[cli::]pin_ptr<cv_qualifier type> var = &initializer;  
```  
  
### Parameter  
 *cv\_qualifier*  
 Qualifizierer `const` oder `volatile`.  Standardmäßig ist ein fester Zeiger `volatile`.  Es ist jedoch redundant kein Fehler, einen festen Zeiger deklarieren `volatile`.  
  
 *type*  
 Der `initializer`\-Typ.  
  
 *var*  
 Der Name der Variablen `pin_ptr`.  
  
 *initializer*  
 Ein Member eines Referenztyps, des Elements eines verwalteten Arrays oder einem anderen Objekt, das auf einem systemeigenen Zeiger zuweisen können.  
  
### Hinweise  
 `pin_ptr` stellt eine Obermenge der Funktionalität eines systemeigenen Zeiger dar.  Daher alles kann, das auf einem systemeigenen Zeiger zugewiesen werden kann, auch zugewiesen sind `pin_ptr`.  Ein innerer Zeiger ist zulässig, um den gleichen Satz von Vorgängen wie systemeigene Zeiger, einschließlich den Vergleich und Zeigerarithmetik auszuführen.  
  
 Ein Objekt oder ein Unterobjekt einer verwalteten Klasse können angeheftet werden, in diesem Fall die Common Language Runtime sie nicht während der Garbage Collection verschoben wird.  Die grundlegende Verwendung dieses ist, einen Zeiger an verwaltete Daten als tatsächliche Parameter eines Funktionsaufrufs nicht verwaltetem zu übergeben.  Während eines Auflistungszyklus untersucht die Laufzeit die Metadaten, die für festen Zeiger erstellt und verschiebt nicht das Element, das auf sie zeigt.  
  
 Ein Objekt, Fixieren fixiert auch seine Wertfelder an; das heißt, Felder von Primitiven oder von Werttyp.  Allerdings werden die Felder, die durch Trackinghandle \(`%`\) deklariert werden nicht fixiert.  
  
 Das Fixieren eines Unterobjekts, das in einem verwalteten Objekt definiert wurde, hat den Auswirkungen des Anheftens des vollständigen Objekts.  
  
 Wenn der feste Zeiger neu zugewiesen wird, um auf einen neuen Wert zu veranschaulichen, wird die vorherige Instanz, auf die verwiesen wird, nicht mehr als fixiert.  
  
 Ein Objekt ist fixiert, nur während `pin_ptr` darauf gezeigt.  Das Objekt wird nicht mehr, fixiert, wenn sein fester Zeiger des Gültigkeitsbereichs, oder wird auf [Nullptr\-Schlüsselwort](../windows/nullptr-cpp-component-extensions.md) festgelegt.  Nachdem `pin_ptr` ungültig wird, kann das Objekt, die angeheftet wurde, in den Heap vom Garbage Collector verschoben werden.  Keine systemeigenen Zeiger, die sich noch im Objekt zeigen, werden nicht aktualisiert, und einen davon Funktionsverweises, könnten eine nicht behebbare Ausnahme auslösen.  
  
 Wenn keine festen Zeiger auf das Objekt alle \(festen Zeiger erloschen den Gültigkeitsbereich, wurden neu zugewiesen, die auf andere Objekte verweisen oder wurden [Nullptr\-Schlüsselwort](../windows/nullptr-cpp-component-extensions.md) zugewiesen\), zeigen, wird das Objekt kann nicht fixiert werden.  
  
 Ein fester Zeiger kann auf einem Bezugshandle, ein Werttyp oder eingepacktes Typhandle, Member eines verwalteten Typs anzeigen bzw. ein Element eines verwalteten Arrays.  Es kann nicht auf einen Referenztyp wird.  
  
 Das Vornehmen der Adresse von `pin_ptr`, die auf einem systemeigenen Objekt zeigt, verursacht nicht definiertes Verhalten.  
  
 Feste Zeiger können als nicht statische lokale Variablen auf dem Stapel nur deklariert werden.  
  
 Feste Zeiger können nicht wie verwendet werden:  
  
-   Funktionsparameter  
  
-   Rückgabetyp einer Funktion  
  
-   Mitglied einer Klasse  
  
-   der Zieltyp einer Umwandlung.  
  
 `pin_ptr` ist im Namespace `cli`.  Weitere Informationen finden Sie unter [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Weitere Informationen zum inneren Zeiger, finden Sie unter [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md).  
  
 Weitere Informationen über feste Zeiger, finden Sie unter [How to: Pin Pointers and Arrays](../windows/how-to-pin-pointers-and-arrays.md) und [How to: Declare Pinning Pointers and Value Types](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird `pin_ptr` verwendet, um die Position des ersten Elements eines Arrays einzuschränken.  
  
```  
// pin_ptr_1.cpp  
// compile with: /clr   
using namespace System;  
#define SIZE 10  
  
#pragma unmanaged  
// native function that initializes an array  
void native_function(int* p) {  
   for(int i = 0 ; i < 10 ; i++)  
    p[i] = i;  
}  
#pragma managed  
  
public ref class A {  
private:  
   array<int>^ arr;   // CLR integer array  
  
public:  
   A() {  
      arr = gcnew array<int>(SIZE);  
   }  
  
   void load() {  
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr  
   int* np = p;   // pointer to the first element in arr  
   native_function(np);   // pass pointer to native function  
   }  
  
   int sum() {  
      int total = 0;  
      for (int i = 0 ; i < SIZE ; i++)  
         total += arr[i];  
      return total;  
   }  
};  
  
int main() {  
   A^ a = gcnew A;  
   a->load();   // initialize managed array using the native function  
   Console::WriteLine(a->sum());  
}  
```  
  
 **Ausgabe**  
  
  **45** **Beispiel**  
  
 Das folgende Beispiel zeigt, dass ein innerer Zeiger zu einem festen Zeiger konvertiert werden kann und dass der Rückgabetyp des address\-of\-Operators \(`&`\) ein innerer Zeiger ist, wenn der Operand auf dem verwalteten Heap ist.  
  
```  
// pin_ptr_2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   G() : i(1) {}  
   int i;  
};  
  
ref struct H {  
   H() : j(2) {}  
   int j;  
};  
  
int main() {  
   G ^ g = gcnew G;   // g is a whole reference object pointer  
   H ^ h = gcnew H;  
  
   interior_ptr<int> l = &(g->i);   // l is interior pointer  
  
   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer  
  
   k = l;   // ok  
   Console::WriteLine(*k);  
};  
```  
  
 **Ausgabe**  
  
 **1** **Beispiel**  
  
 Das folgende Beispiel zeigt, dass ein fester Zeiger auf einen anderen Typ umgewandelt werden kann.  
  
```  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr< int > pt = &mt->i;  
   *pt = 8;  
   Console::WriteLine(mt->i);  
  
   char *pc = ( char* ) pt;  
   *pc = 255;  
   Console::WriteLine(mt->i);  
}  
```  
  
 **Ausgabe**  
  
 **8**   
**255**
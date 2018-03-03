---
title: Pin_ptr (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7205718a3564a3929fe2a9f8b7d8049a320ae1cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
Deklariert eine *feste Zeiger*, der nur mit der common Language Runtime verwendet wird.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 (Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 (Diese Sprachfunktion wird in der Windows-Runtime nicht unterstützt.)  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Ein *feste Zeiger* ein inneren Zeigers, der verhindert, das Objekt dass verweist auf dem Heap der Garbage Collection verschoben. Der Wert, der einen festen Zeiger ist, also nicht von der common Language Runtime geändert. Dies ist erforderlich, wenn Sie die Adresse einer verwalteten Klasse an eine nicht verwaltete Funktion übergeben, sodass die Adresse nicht unerwartet während der Auflösung des nicht verwalteten Funktionsaufrufs ändert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>Parameter  
 *cv_qualifier*  
 `const`oder `volatile` Qualifizierer. Standardmäßig ist ein fester Zeiger `volatile`. Es ist jedoch nicht um einen Fehler, deklarieren einen festen Zeiger redundant `volatile`.  
  
 *Typ*  
 Der `initializer`-Typ.  
  
 *var*  
 Der Name des der `pin_ptr` Variable.  
  
 *initializer*  
 Ein Element ein Verweistyp, ein Element ein verwaltetes Array oder ein anderes Objekt, das einen systemeigenen Zeiger zugewiesen werden können.  
  
### <a name="remarks"></a>Hinweise  
 Ein `pin_ptr` eine Obermenge der Funktionen der systemeigenen Zeiger darstellt. Aus diesem Grund kann Elemente, die einen systemeigenen Zeiger zugewiesen werden kann auch zum zugewiesen eine `pin_ptr`. Ein innerer Zeiger ist zulässig, um den gleichen Satz von Vorgängen wie systemeigene Zeiger, einschließlich Vergleich und Zeigerarithmetik auszuführen.  
  
 Ein Objekt oder untergeordnete Objekt einer verwalteten Klasse kann angeheftet werden in diesem Fall wird die common Language Runtime nicht es während der Garbagecollection verschoben. Hauptverwendungszweck für diese ist einen Zeiger auf verwaltete Daten, die als übergebener Parameter eines nicht verwalteten Funktionsaufrufs zu übergeben. Während einer Collection-Zyklus die Laufzeit überprüfen Sie die Metadaten für die feste Zeiger erstellt wird und das Element, auf die verwiesen, wird nicht verschoben.  
  
 Anheften eines Objekts pins auch die Wertfelder; d. h. type Felder von primitiven oder Wert. Allerdings deklariert Felder von Trackinghandle (`%`) nicht angeheftet werden.  
  
 Anheften eines untergeordneten Objekts in ein verwaltetes Objekt definierten wirkt sich das anheften als ganze Objekt aus.  
  
 Wenn der feste Zeiger neu zugewiesen wird, um einen neuen Wert zu verweisen, die vorherige Instanz, auf die gezeigt wird nicht mehr als fixiert betrachtet.  
  
 Ein Objekt fixiert ist nur eine `pin_ptr` darauf verweist. Das Objekt ist nicht mehr fixiert, wenn der feste Zeiger den Gültigkeitsbereich verlässt oder auf festgelegt ist [Nullptr](../windows/nullptr-cpp-component-extensions.md). Nach der `pin_ptr` sinkt außerhalb des gültigen Bereichs, das Objekt, das angeheftet wurde im Heap durch den Garbage Collector verschoben werden können. Jeder systemeigene Zeiger, die weiterhin auf das Objekt verweisen werden nicht aktualisiert werden, und Verweises auf eine von ihnen konnte eine nicht behebbare Ausnahme auslösen.  
  
 Wenn keine feste Zeiger auf das Objekt verweisen (alle feste Zeiger ist ein Fehler aufgetreten, außerhalb des gültigen Bereichs, zugewiesen wurden, um auf andere Objekte verweisen oder zugewiesen wurden [Nullptr](../windows/nullptr-cpp-component-extensions.md)), das Objekt ist garantiert nicht angeheftet werden.  
  
 Ein fester Zeiger verweisen auf einen Verweis Handle Werttyp oder mittels Boxing gepackter Typhandle, Member eines verwalteten Typs oder ein Element von einem verwalteten Array. Es kann nicht auf einen Verweistyp verweisen.  
  
 Übernahme der Adresse einer `pin_ptr` , verweist auf ein systemeigenes Objekt verursacht nicht definiertes Verhalten.  
  
 Feste Zeiger können nur auf dem Stapel als nicht statische lokale Variablen deklariert werden.  
  
 Feste Zeiger können nicht als verwendet werden:  
  
-   Funktionsparameter  
  
-   der Rückgabetyp einer Funktion  
  
-   ein Member einer Klasse  
  
-   der Zieltyp einer Typumwandlung.  
  
 `pin_ptr`befindet sich in der `cli` Namespace. Weitere Informationen finden Sie unter [Plattform, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Weitere Informationen zu inneren Zeigern, finden Sie unter [Interior_ptr (C + c++ / CLI)](../windows/interior-ptr-cpp-cli.md).  
  
 Weitere Informationen zum Festhalten von Zeigern, finden Sie unter [wie: Anheften von Zeigern und Arrays](../windows/how-to-pin-pointers-and-arrays.md) und [wie: Deklarieren Festhalten von Zeigern und Werttypen](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird `pin_ptr` , die die Position des ersten Elements eines Arrays zu beschränken.  
  
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
  
```Output  
45  
```  
  
 **Beispiel**  
  
 Das folgende Beispiel zeigt, dass ein innerer Zeiger zu einem festen Zeiger konvertiert werden kann und der Rückgabetyp des Address-of-Operators (`&`) wird ein innerer Zeiger, wenn der Operand auf dem verwalteten Heap ist.  
  
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
  
```Output  
1  
```  
  
 **Beispiel**  
  
 Das folgende Beispiel zeigt, dass ein fester Zeiger in einen anderen Typ umgewandelt werden kann.  
  
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
  
```Output  
8  
255  
```
---
title: Pin_ptr (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a87dadfd4787e4bd0100efb8fe7ffe2b1e7a8899
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607851"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)
Deklariert eine *festen Zeiger*, das verwendet wird, nur mit der common Language Runtime.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 (Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 (Diese Sprachfunktion wird in der Windows-Runtime nicht unterstützt.)  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Ein *festen Zeiger* ein innerer Zeiger, der verhindert, das Objekt dass verweist auf dem Heap der Garbage Collection verschoben. Der Wert, der einen festen Zeiger ist, also nicht von der common Language Runtime geändert werden. Dies ist erforderlich, wenn Sie die Adresse einer verwalteten Klasse an eine nicht verwaltete Funktion übergeben, damit, dass die Adresse nicht unerwartet während der Auflösung des nicht verwalteten Funktionsaufrufs ändert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;  
```  
  
### <a name="parameters"></a>Parameter  
 *cv_qualifier*  
 **const** oder **flüchtige** Qualifizierer. Standardmäßig ist ein fester Zeiger **flüchtige**. Es ist redundant, jedoch nicht um einen Fehler, deklarieren einen festen Zeiger **flüchtige**.  
  
 *Typ*  
 Der Typ des *Initialisierer*.  
  
 *var*  
 Der Name des der **Pin_ptr** Variable.  
  
 *initializer*  
 Ein Member eines Verweistyps, Element eines verwalteten Arrays oder jedes andere Objekt, das Sie in einen systemeigenen Zeiger zuweisen können.  
  
### <a name="remarks"></a>Hinweise  
 Ein **Pin_ptr** eine Obermenge der Funktionen der einen systemeigenen Zeiger darstellt. Aus diesem Grund Elemente, die in einen systemeigenen Zeiger zugewiesen werden, kann auch zugewiesen werden eine **Pin_ptr**. Ein innerer Zeiger ist zulässig, um den gleichen Satz von Vorgängen wie systemeigene Zeiger, einschließlich Vergleich und Zeigerarithmetik auszuführen.  
  
 Ein Objekt oder untergeordnete Objekt einer verwalteten Klasse kann angeheftet werden in diesem Fall wird die common Language Runtime nicht es während der Garbagecollection verschoben. Hauptverwendungszweck für diese ist einen Zeiger auf die verwaltete Daten, die als übergebener Parameter eines nicht verwalteten Funktionsaufrufs zu übergeben. Während einer Collection-Zyklus, der die Laufzeit prüft die Metadaten für den festen Zeiger erstellt und ändert sich nicht auf das Element, dem es verweist.  
  
 Anheften eines Objekts befestigt auch die Wertfelder; Felder des primitiven oder Wert, also geben zu können. Allerdings Felder definiert, indem Trackinghandle (`%`) sind nicht verknüpft.  
  
 Anheften von einem untergeordneten Objekt in ein verwaltetes Objekt definiert, hat die Auswirkung der Verknüpfung mit dem das gesamte Objekt.  
  
 Wenn der feste Zeiger neu zugewiesen wird, um einen neuen Wert zu verweisen, die vorherige Instanz gezeigt wird nicht mehr als fixiert.  
  
 Ein Objekt fixiert ist zwar nur eine **Pin_ptr** darauf verweist. Das Objekt ist nicht mehr fixiert, wenn der feste Zeiger den Gültigkeitsbereich verlässt oder NA hodnotu nastaven ["nullptr"](../windows/nullptr-cpp-component-extensions.md). Nach der **Pin_ptr** wurde außerhalb des gültigen Bereichs, der das Objekt, das angeheftet wurde im Heap vom Garbage Collector verschoben werden können. Systemeigene Zeiger, die nach wie vor auf das Objekt verweisen werden nicht aktualisiert werden, und Entfernen des Verweises auf eine von ihnen könnte eine nicht behebbare Ausnahme auslösen.  
  
 Wenn keine festen Zeiger auf das Objekt verweisen (alle festen Zeiger ist, die außerhalb des gültigen Bereichs ein Fehler aufgetreten, zugewiesen wurden, um auf andere Objekte verweisen oder zugewiesen wurden ["nullptr"](../windows/nullptr-cpp-component-extensions.md)), das Objekt ist definitiv nicht angeheftet werden.  
  
 Ein fester Zeiger kann auf eine Verweis-Handle, Werttyp oder geschachtelten Typs-Handle, Member eines verwalteten Typs oder ein Element eines verwalteten Arrays zeigen. Es kann nicht auf einen Verweistyp verweisen.  
  
 Übernehmen der Adresse einer **Pin_ptr** verweist auf ein systemeigenes Objekt führt dazu, dass nicht definiertem Verhalten.  
  
 Feste Zeiger können nur auf dem Stapel als nicht statische lokale Variablen deklariert werden.  
  
 Feste Zeiger können nicht als verwendet werden:  
  
-   Funktionsparameter  
  
-   der Rückgabetyp einer Funktion  
  
-   ein Member einer Klasse  
  
-   der Zieltyp einer Typumwandlung.  
  
 **Pin_ptr** befindet sich in der `cli` Namespace. Weitere Informationen finden Sie unter [Platform-, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Weitere Informationen zu inneren Zeigern, finden Sie unter [Interior_ptr (C++ / CLI)](../windows/interior-ptr-cpp-cli.md).  
  
 Weitere Informationen zu Festhalten von Zeigern, finden Sie unter [Vorgehensweise: Anheften von Zeigern und Arrays](../windows/how-to-pin-pointers-and-arrays.md) und [wie: Deklarieren Anheften von Zeigern und Werttypen](../windows/how-to-declare-pinning-pointers-and-value-types.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/clr`  
  
### <a name="examples"></a>Beispiele  
  
 Im folgenden Beispiel wird **Pin_ptr** um die Position des ersten Elements eines Arrays zu beschränken.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt, dass ein innerer Zeiger zu einem festen Zeiger konvertiert werden kann und der Rückgabetyp des Address-of-Operators (`&`) ein innerer Zeiger ist, wenn der Operand, auf dem verwalteten Heap ist.  
  
```cpp  
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
  
 Das folgende Beispiel zeigt, dass ein fester Zeiger in einen anderen Typ umgewandelt werden kann.  
  
```cpp  
// pin_ptr_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class ManagedType {  
public:  
   int i;  
};  
  
int main() {  
   ManagedType ^mt = gcnew ManagedType;  
   pin_ptr<int> pt = &mt->i;  
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
---
title: Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5e2faf56f050610e6c98ff82cdca10333a54fd93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen
Dieses Thema erläutert die Ausnahmebehandlung in verwalteten Anwendungen. D. h. eine Anwendung, die die Kompilierung mit der **"/ CLR"** -Compileroption.  
  
## <a name="in-this-topic"></a>In diesem Thema  
  
-   [Auslösen von Ausnahmen unter/CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Try/Catch-Blöcke für CLR-Erweiterungen](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>Hinweise  
 Beim Kompilieren mit der **"/ CLR"** -Option können Sie CLR-Ausnahmen als auch für Standard behandeln [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md) und [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md) (SEH). Eine CLR-Ausnahme ist, jede Ausnahme, die von einem verwalteten Typ ausgelöst. Die [System:: Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) Klasse bietet viele nützliche Methoden für die Verarbeitung von CLR-Ausnahmen und wird als eine Basisklasse für benutzerdefinierte Ausnahmeklassen empfohlen.  
  
 Abfangen von Ausnahmetypen, die von einer Schnittstelle abgeleitet wird unter unterstützt **"/ CLR"**. Darüber hinaus lässt die common Language Runtime nicht zu Sie zum Abfangen von Ausnahmen für Stapelüberläufe; Stapelüberlauf-Ausnahmen wird der Prozess beendet.  
  
 Weitere Informationen über die Unterschiede in der Behandlung von Ausnahmen in verwalteten und nicht verwalteten Anwendungen finden Sie unter [Unterschiede in der Ausnahme behandeln von Verhalten unter Managed Extensions for C++](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>Auslösen von Ausnahmen unter/CLR  
 Der C++-Throw-Ausdruck wird erweitert, um ein Handle auf einem CLR-Typ zu lösen. Im folgenden Beispiel wird einen benutzerdefinierter Ausnahmetyp erstellt und löst dann eine Instanz dieses Typs:  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 Ein Werttyp muss geschachtelt werden, vor dem ausgelöst wird:  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Try/Catch-Blöcke für CLR-Erweiterungen  
 Die gleiche **versuchen**/**catch** Blockstruktur für abgefangen, CLR- und systemeigenen Ausnahmen verwendet werden kann:  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### <a name="output"></a>Ausgabe  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### <a name="order-of-unwinding-for-c-objects"></a>Reihenfolge der Entladung für C++-Objekte  
 Entladung tritt für alle C++-Objekte mit Destruktoren führen, die möglicherweise auf dem Stapel zur Laufzeit zwischen der auslösenden und die Behandlungsfunktion. Da CLR-Typen auf dem Heap reserviert werden, gilt was die Entladung nicht für sie.  
  
 Die Reihenfolge der Ereignisse für eine ausgelöste Ausnahme lautet wie folgt:  
  
1.  Die Common Language Runtime führt den Stapel suchen, für die entsprechenden Catch-Klausel oder im Fall von SEH, eine mit Ausnahme der Filter für SEH, um die Ausnahme abzufangen. Catch-Klauseln werden zuerst in der lexikalischen Reihenfolge durchsucht, und dann dynamisch nach unten der Aufrufliste.  
  
2.  Nachdem die richtige Handler gefunden wird, ist der Stapel entladen, bis zu diesem Zeitpunkt. Für jeden Funktionsaufruf im Stapel, werden seine lokale Objekte zerstört und __finally Blöcke ausgeführt werden, von den meisten nach außen geschachtelt.  
  
3.  Nachdem der Stapel entladen wird, wird die Catch-Klausel ausgeführt.  
  
### <a name="catching-unmanaged-types"></a>Nicht verwaltete Typen abfangen  
 Wenn ein Typ nicht verwaltete Objekt ausgelöst wird, wird Sie mit einer Ausnahme vom Typ umschlossen [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx). Bei der Suche nach der entsprechenden **catch** -Klausel, es gibt zwei Möglichkeiten.  
  
-   Wenn ein systemeigener C++-Typ festgestellt wird, wird die Ausnahme entpackt und im Vergleich zu den Typ gefunden. Dieser Vergleich kann einen systemeigenen C++-Typ, der auf die übliche Weise abgefangen werden.  
  
-   Jedoch, wenn eine **catch** Klausel vom Typ **SEHException** oder eine der zugehörigen Basisklassen wird zuerst überprüft, die-Klausel wird die Ausnahme abzufangen. Aus diesem Grund sollten Sie alle Catch-Klauseln platzieren, die systemeigene C++-Typen abfangen, vor einem-Klauseln der CLR-Typen catch.  
  
 Hinweis  
  
```  
catch(Object^)  
```  
  
 und  
  
```  
catch(...)  
```  
  
 sowohl werden alle ausgelösten Typ einschließlich SEH-Ausnahmen abfangen.  
  
 Wenn Sie ein nicht verwalteter Typ durch catch(Object^) abgefangen wird, werden nicht die ausgelöste Objekt zerstört.  
  
 Wenn das Auslösen und Abfangen von Ausnahmen nicht verwaltet, wir empfehlen die Verwendung der [/EHsc /](../build/reference/eh-exception-handling-model.md) -Compileroption anstelle von **/EHs** oder **/EHa**.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)   
 ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)
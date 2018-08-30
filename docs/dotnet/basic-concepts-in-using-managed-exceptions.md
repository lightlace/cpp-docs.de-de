---
title: Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ad3b00367be086bfe6e011b0d3aa7b93805eb103
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202045"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen
Dieses Thema beschreibt die Behandlung von Ausnahmen in verwalteten Anwendungen. D. h. eine Anwendung, die die Kompilierung mit der **"/ CLR"** -Compileroption.  
  
## <a name="in-this-topic"></a>In diesem Thema  
  
-   [Auslösen von Ausnahmen unter/CLR](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Try/Catch-Blöcke für CLR-Erweiterungen](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>Hinweise  
 Bei der Kompilierung mit der **"/ CLR"** auswählen, können Sie CLR-Ausnahmen als auch Standard behandeln [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md) und [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md) (SEH). Eine CLR-Ausnahme ist eine Ausnahme, die von einem verwalteten Typ ausgelöst. Die [System:: Exception](https://msdn.microsoft.com/library/system.exception.aspx) -Klasse bietet viele nützliche Methoden für die Verarbeitung von CLR-Ausnahmen und wird als eine Basisklasse für benutzerdefinierte Ausnahmeklassen empfohlen.  
  
 Abfangen von Ausnahmetypen, die von einer Schnittstelle abgeleitet wird unter unterstützt **"/ CLR"**. Darüber hinaus lässt die common Language Runtime nicht zu Stapelüberlauf-Ausnahmen zu erfassen; eine Stapelüberlaufausnahme wird den Prozess beendet.  
  
 Weitere Informationen zu Unterschieden bei der Behandlung von Ausnahmen in verwalteten und nicht verwalteten Anwendungen finden Sie unter [Unterschiede in der Ausnahme behandeln Verhalten in Managed Extensions für C++](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> Auslösen von Ausnahmen unter/CLR  
 Die C++-Throw-Ausdrucks wird erweitert, um ein Handle in einem CLR-Typ auslösen. Das folgende Beispiel erstellt einen benutzerdefinierten Ausnahmetyp und löst anschließend eine Instanz dieses Typs:  
  
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
  
 Ein Werttyp muss geschachtelt werden, bevor ausgelöst wird:  
  
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
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Try/Catch-Blöcke für CLR-Erweiterungen  
 Dasselbe **versuchen**/**catch** Blockstruktur zum Abfangen von CLR- und systemeigene Ausnahmen verwendet werden kann:  
  
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
 Entladen tritt auf, für alle C++-Objekte mit Destruktoren, die auf dem Stapel Laufzeit zwischen der auslösende Funktion und die Behandlungsfunktion sein können. Da CLR-Typen auf dem Heap reserviert werden, gilt entladen nicht für sie.  
  
 Die Reihenfolge der Ereignisse für eine ausgelöste Ausnahme lautet wie folgt aus:  
  
1.  Die Laufzeit führt den Stapel suchen, für die betreffende Catch-Klausel oder im Fall von SEH, eine mit Ausnahme der Filter für SEH, um die Ausnahme abzufangen. Catch-Klauseln werden zuerst in der lexikalischen Reihenfolge durchsucht, und dann dynamisch nach unten der Aufrufliste.  
  
2.  Nachdem Sie der richtige Handler gefunden wird, ist der Stapel entladen, bis zu diesem Zeitpunkt. Für jeden Funktionsaufruf im Stapel, die lokalen Objekte zerstört werden, und __finally Blöcke ausgeführt werden, von den meisten nach außen geschachtelt.  
  
3.  Nachdem der Stapel entladen wird, wird die Catch-Klausel ausgeführt.  
  
### <a name="catching-unmanaged-types"></a>Abfangen von nicht verwalteten Typen  
 Wenn ein Typ nicht verwaltete Objekt ausgelöst wird, wird es mit einer Ausnahme vom Typ umschlossen [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx). Bei der Suche nach den entsprechenden **catch** -Klausel, es gibt zwei Möglichkeiten.  
  
-   Wenn ein systemeigener C++-Typ gefunden wird, wird die Ausnahme entpackt und im Vergleich zu den gefundenen Typs. Dieser Vergleich kann es sich um einen systemeigenen C++-Typ, der auf die übliche Weise abgefangen werden.  
  
-   Aber wenn eine **catch** Klausel vom Typ **SEHException-Ausnahme** oder einer seiner Basisklassen wird zunächst untersucht, die Klausel fängt die Ausnahme. Aus diesem Grund sollten Sie alle Catch-Klauseln platzieren, die systemeigene C++-Typen abfangen, vor alle Klauseln der CLR-Typen abfangen.  
  
 Hinweis  
  
```  
catch(Object^)  
```  
  
 und  
  
```  
catch(...)  
```  
  
 Beide werden jeden ausgelösten einschließlich SEH-Ausnahmen abfängt.  
  
 Wenn ein nicht verwalteter Typ von catch(Object^) abgefangen wird, werden sie nicht das ausgelöste Objekt zerstört.  
  
 Wenn das Auslösen und Abfangen von Ausnahmen nicht verwaltet, wir empfehlen die Verwendung der [/EHsc](../build/reference/eh-exception-handling-model.md) -Compileroption anstelle von **/EHs** oder **/EHa**.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)   
 ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)
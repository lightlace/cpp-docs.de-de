---
title: "Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally-Schlüsselwort, Verwaltete Ausnahmen"
  - "catch-Blöcke"
  - "Ausnahmen, Verwaltet"
  - "Auslösen von Ausnahmen, Verwaltete Ausnahmen"
  - "try-catch-Ausnahmebehandlung"
  - "try-catch-Ausnahmebehandlung, Verwaltete Anwendungen"
  - "Visual C++, Behandeln von verwalteten Ausnahmen"
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema erläutert Ausnahmebehandlung in verwalteten Anwendungen.  Das bedeutet, eine Anwendung, die mit der **\/clr**\-Compileroption kompiliert wird.  
  
## In diesem Thema  
  
-   [Auslösen von Ausnahmen unter \/clr](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Try\/catch\-Blöcke für CLR\-Erweiterungen](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## Hinweise  
 Wenn Sie mit der **\/clr** \- Option kompilieren, können Sie CLR\-Ausnahmen sowie standardmäßige [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md) und [strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md) \(SEH\) behandeln.  Eine CLR\-Ausnahme ist jede Ausnahme, die durch einen verwalteten Typ ausgelöst wird.  Die [System::Exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx)\-Klasse stellt viele nützliche Methoden zum Verarbeiten von CLR\-Ausnahmen bereit und wird als Basisklasse für benutzerdefinierte Ausnahmeklassen empfohlen.  
  
 Die Ausnahmetypen, die von einer Schnittstelle abgeleitet werden, wird unter **\/clr** nicht unterstützt.  Für die Common Language Runtime ermöglicht Sie nicht, Ausnahmen für Stapelüberläufe abzufangen; eine Stapelüberlaufausnahme beendet den Prozess.  
  
 Weitere Informationen zu Unterschieden bei der Ausnahmebehandlung in verwalteten und nicht verwalteten Anwendungen, finden Sie unter [Unterschiede im Ausnahmebehandlungs\-Verhaltens unter Managed Extensions for C\+\+](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> Auslösen von Ausnahmen unter \/clr  
 Der C\+\+\-Wurfsausdruck wird erweitert, um ein Handle auf einen CLR\-Typ auszulösen.  Im folgenden Beispiel wird einem benutzerdefinierten Ausnahmetyp und anschließend eine Instanz dieses Typs aus:  
  
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
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Try\/catch\-Blöcke für CLR\-Erweiterungen  
 Gleiche **try**\/**catch**\-Blockstruktur können zum Abfangen von CLR und systemeigener Ausnahmen verwendet werden:  
  
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
  
### Ausgabe  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### Reihenfolge der für C\+\+\-Objekte Entladung  
 Entladen tritt für alle C\+\+\-Objekte mit Destruktoren auf, die möglicherweise im Laufzeitkellerspeicher zwischen der auslösenden Funktion und der Behandlungsfunktion sind.  Da auf CLR\-Typen dem Heap zugeordnet sind, gilt beim Entladen nicht auf sie zu.  
  
 Die Reihenfolge der Ereignisse für eine Ausnahme ist, wie folgt:  
  
1.  Die Laufzeit ausgeführt wird den Stapel durch, die nach der entsprechenden catch\-Klausel oder im Fall SEH sucht, außer für Filter SEH, um die Ausnahme abzufangen.  Catch\-Klauseln werden zuerst in der lexikalischen Reihenfolge und dann dynamisch die Abwärtsumwandlung Aufrufliste gefunden.  
  
2.  Sobald der richtige Handler, der Stapel entladen wird zu diesem Punkt gefunden.  Für jeden Funktionsaufruf auf dem Stapel, werden ihre lokalen Objekte zerstört und \_\_finally werden Blöcke ausgeführt, der nach außen geschachtelt.  
  
3.  Sobald wird der Stapel entladen, die catch\-Klausel wird ausgeführt.  
  
### Verwaltete nicht verwalteter Typen  
 Wenn ein nicht verwalteter Objekttyp ausgelöst wird, wird er mit einer Ausnahme vom Typ [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx) umschlossen.  Beim Suchen für die entsprechende **catch**\-Klausel, gibt es zwei Möglichkeiten.  
  
-   Wenn ein systemeigenes C\+\+\-Typ erreicht wird, wird die Ausnahme an den auftretenden wurde Typ ausgepackt und verglichen.  Dieser Vergleich können einen systemeigenen normal aufgefangen werden C\+\+\-Typ.  
  
-   Wenn **catch** eine Klausel des Typs **SEHException** oder eine ihrer Basisklassen zuerst untersucht wird, fängt die Klausel die Ausnahme ab.  Daher sollten Sie alle catch\-Klauseln platzieren, die systemeigenen C\+\+\-Typen zuerst abfangen, bevor alle catch\-Klauseln von CLR.  
  
 Hinweis  
  
```  
catch(Object^)  
```  
  
 und  
  
```  
catch(...)  
```  
  
 fangen beide einen ausgelösten Typ einschließlich SEH Ausnahmen ab.  
  
 Wenn ein nicht verwalteter Typ von catch \(Object^\) abgefangen wird, zerstört nicht das ausgelöste Objekt.  
  
 Wenn wir nicht verwaltete Ausnahmen, empfohlen ausgelöst oder abgefangen werden, dass Sie die Compileroption [\/EHsc](../build/reference/eh-exception-handling-model.md) anstelle von **\/EHs** oder **\/EHa** verwenden.  
  
## Siehe auch  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)
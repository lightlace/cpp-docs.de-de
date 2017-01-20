---
title: "Ein Trackinghandle f&#252;r einen geschachtelten Wert"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Geschachtelte Werttypen, Trackinghandle für"
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Ein Trackinghandle f&#252;r einen geschachtelten Wert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Verwendung eines Trackinghandles zum Verweisen auf einen Werttyp hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Boxing ist eine Besonderheit des vereinheitlichten Typsystems von CLR.  Werttypen enthalten ihren Zustand direkt, während Referenztypen ein implizites Paar darstellen: Die benannte Entität ist ein Handle zu einem unbenannten Objekt, das auf dem verwalteten Heap zugeordnet wird.  Eine Initialisierung oder Zuweisung eines Werttyps zu einem `Object` zum Beispiel erfordert, dass der Werttyp innerhalb des CLR\-Heaps platziert wird \(der Werttyp wird bildlich gesprochen verpackt, daher die Bezeichnung Boxing\). Dabei wird zuerst der zugeordnete Speicher belegt, dann der Zustand des Werttyps kopiert und anschließend die Adresse dieses anonymen Wert\/Referenz\-Hybrids zurückgegeben.  Wenn daher in C\# der folgende Code geschrieben wird:  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 laufen wesentlich mehr Vorgänge ab, als aufgrund der Einfachheit des Codes zu vermuten gewesen wäre.  Der Aufbau der Programmiersprache C\# verbirgt nicht nur die Komplexität der Vorgänge, die unter der Oberfläche ablaufen, sondern auch die Abstraktion des Boxings.  In Managed Extensions for C\+\+ dagegen wird davon ausgegangen, dass die höhere Effizienz bei der Programmierung nur auf Kosten anderer Programmieraspekte erreicht werden kann. Deshalb werden hier explizite Anweisungen vom Benutzer erwartet.  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Boxing ist in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] implizit:  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 Das `__box`\-Schlüsselwort dient in Managed Extensions einem zweiten, wichtigeren Dienst, der in Sprachen wie C\# und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] entwurfsbedingt fehlt: Er bietet sowohl ein Vokabular als auch einen Trackinghandle zur direkten Bearbeitung von geschachtelten Instanzen im verwalteten Heap.  Betrachten Sie z. B. das folgende kleine Programm:  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 Der zugrunde liegende Code für die drei Aufrufe von `WriteLine` zeigt den unterschiedlichen Aufwand, der durch den Zugriff auf den Wert eines geschachtelten Werttyps entsteht \(besonderer Dank gilt hier Yves Dolce, der diese Unterschiede deutlich gemacht hat\). Die angegebenen Zeilen zeigen den Zusatzaufwand, den jeder Aufruf mit sich bringt.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 Die direkte Übergabe des geschachtelten Werttyps an `Console::WriteLine` macht sowohl das Boxing als auch den Aufruf von `ToString()` überflüssig. \(Natürlich ist ein vorheriges Boxing erforderlich, um `br` zu initialisieren, wir gewinnen also nichts, solange `br` nicht wirklich eingesetzt wird.\)  
  
 In der neuen Syntax wurde die Unterstützung für geschachtelte Werttypen wesentlich eleganter gelöst und in das Typsystem integriert, ohne dabei die Leistungsfähigkeit zu verringern.  Das folgende Beispiel zeigt die Übersetzung des obigen kleinen Programms:  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## Siehe auch  
 [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Gewusst wie: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)
---
title: "Ein Trackinghandle für einen geschachtelten Wert | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a986dcea2eec183ae09eb9af275082922257ef76
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Ein Trackinghandle für einen geschachtelten Wert
Die Verwendung von ein Trackinghandle für einen Werttyp-Verweis hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 Beim Boxing handelt es sich um eine Besonderheit des Typsystems unified CLR. Werttypen enthalten ihren Zustand direkt, während Referenztypen ein implizites Paar sind: die benannte Entität ist ein Handle für ein unbenanntes Objekt im verwalteten Heap belegt. Eine Initialisierung oder Zuweisung eines Werts, geben eine `Object`, z. B. erfordert, dass der Werttyp innerhalb der CLR-Heap - Dies ist, in dem das Abbild des boxing es entsteht - platziert werden zunächst nach der zugeordneten Speicher belegen, und dann durch Kopieren der Werttyp Zustand , und klicken Sie dann die Adresse dieser anonyme Wert/Verweis hybride zurückgeben. Deshalb, wenn eine in c# schreibt  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 Es ist ein hervorragendes Weitere erfolgen, als durch die Einfachheit des Codes offensichtlich hergestellt wird. Der Entwurf der C#-verbirgt die Komplexität nicht nur aus Vorgängen hinter den Kulissen durchgeführt werden, sondern auch die Abstraktion von boxing selbst. In Managed Extensions for C++, andererseits, Bedenken Sie, dass dies bewirken, dass auf "false" Sinne der Effizienz des Benutzers Fläche ablegt, durch das explizite Anweisung anfordern:  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Boxing ist implizit in Visual C++:  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 Die `__box` -Schlüsselwort dient in Managed Extensions eine, die nicht vorhanden ist einen wichtigen Dienst Entwurfs von Sprachen wie c# und Visual Basic: bietet ein Vokabular und die Überwachung für eine geschachtelte Instanz auf dem verwalteten Heap direkt bearbeiten behandeln. Betrachten Sie beispielsweise das folgende kleine Programm:  
  
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
  
 Die zugrunde liegende Code für die drei Aufrufe der `WriteLine` anzeigen, die verschiedene Kosten für den Zugriff auf den Wert des einem geschachtelten Wert Geben Sie (Dank Yves hier Dolce, hat diese Unterschiede), in denen die angegebenen Zeilen den Mehrbedarf in Verbindung mit jedem zeigen, Aufruf.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
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
  
 Übergeben direkt an den geschachtelten Werttyp `Console::WriteLine` eliminiert sowohl das Boxing aufzurufenden `ToString()`. (Natürlich, besteht der frühere Boxing initialisieren `br`, sodass wir alles erhalten nicht, es sei denn, die wir uns tatsächlich konzentrieren `br` arbeiten.  
  
 In der neuen Syntax ist die Unterstützung für geschachtelte Werttypen erheblich mehr elegante und in das Typsystem integriert und deren Möglichkeiten beibehalten. Hier ist z. B. die Übersetzung des früheren small-Programms:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Werttypen und ihr Verhalten (C + c++ / CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)
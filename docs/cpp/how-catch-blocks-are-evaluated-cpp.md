---
title: "Auswerten von Catch-Bl&#246;cken (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++-Ausnahmebehandlung, catch-Handler"
  - "catch-Schlüsselwort [C++], Typen von catch-Handlern"
  - "Ausnahmebehandlung, Abfangen und Löschen von Ausnahmen"
  - "try-catch-Schlüsselwort [C++], Catchable-Typen"
  - "Typen [C++], Ausnahmebehandlung"
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Auswerten von Catch-Bl&#246;cken (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ ermöglicht Ihnen das Auslösen von Ausnahmen eines beliebigen Typs, obwohl im Allgemeinen empfohlen wird, Typen auszulösen, die von der std::exception abgeleitet sind.  Eine C\+\+\-Ausnahme kann von einem **catch**\-Handler abgefangen werden, der denselben Typ wie die ausgelöste Ausnahme angibt, oder von einem Handler, der jeden Typ von Ausnahme abfangen kann.  
  
 Wenn der Typ der ausgelösten Ausnahme eine Klasse ist, die auch eine Basisklasse \(oder Klassen\) besitzt, kann sie durch Handler abgefangen werden, die Basisklassen des Ausnahmetyps oder Verweise auf Basen des Ausnahmetyps akzeptieren.  Beachten Sie, dass wenn eine Ausnahme durch einen Verweis abgefangen wird, sie an das tatsächlich ausgelöste Ausnahmeobjekt gebunden ist; andernfalls ist es eine Kopie \(nahezu identisch mit einem Argument für eine Funktion\).  
  
 Wenn eine Ausnahme ausgelöst wird, wird sie durch die folgenden Typen von **catch**\-Handlern abgefangen:  
  
-   Ein Handler, der jeden Typ akzeptieren kann \(mit der Auslassungszeichensyntax\).  
  
-   Ein Handler, der den gleichen Typ wie das Ausnahmeobjekt akzeptiert. Da es eine Kopie ist, werden **const**\- und `volatile`\-Modifizierer ignoriert.  
  
-   Ein Handler, der einen Verweis auf den gleichen Typ wie das Ausnahmeobjekt akzeptiert.  
  
-   Ein Handler, der einen Verweis auf ein **const**\- oder `volatile`\-Format vom gleichen Typ wie das Ausnahmeobjekt akzeptiert.  
  
-   Ein Handler, der eine Basisklasse akzeptiert, die dem gleichen Typ des Ausnahmeobjekts entspricht. Da es eine Kopie ist, werden **const**\- und `volatile`\-Modifizierer ignoriert.  Der **catch**\-Handler für eine Basisklasse muss nicht vor dem **catch**\-Handler für die abgeleitete Klasse stehen.  
  
-   Ein Handler, der einen Verweis auf eine Basisklasse des gleichen Typs wie das Ausnahmeobjekt akzeptiert.  
  
-   Ein Handler, der einen Verweis auf ein **const**\- oder `volatile`\-Format einer Basisklasse vom gleichen Typ wie das Ausnahmeobjekt akzeptiert.  
  
-   Ein Handler, der einen Zeiger akzeptiert, in den ein ausgelöstes Zeigerobjekt über Standardzeigerkonvertierungsregeln konvertiert werden kann.  
  
 Die Reihenfolge der **catch**\-Handlers ist wichtig, denn Handler für einen bestimmten **try**\-Block werden der Reihe nach untersucht.  Beispielsweise ist es einem Fehler, den Handler einer Basisklasse vor dem Handler einer abgeleiteten Klasse zu platzieren.  Nachdem ein entsprechender **catch**\-Handler gefunden wird, werden nachfolgende Handler nicht überprüft.  Daher muss es sich bei einem Auslassungszeichen\-**catch**\-Handler um den letzte Handler für dessen **try**\-Block handeln.  Beispiel:  
  
```  
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 In diesem Beispiel ist der Auslassungszeichen\-**catch**\-Handler der einzige Handler, der überprüft wird.  
  
## Siehe auch  
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
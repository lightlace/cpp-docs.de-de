---
title: "Verwaltete Typen (C++/CL)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "__gc-Typen"
  - "Typen [C++], CLR"
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Verwaltete Typen (C++/CL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax für die Deklaration verwalteter Typen und die Erstellung und Verwendung von Objekten dieser Typen hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ wesentlich geändert.  Der Sinn dieser Änderungen besteht darin, die Integration der verwalteten Typen in das ISO\-C\+\+\-Typsystem zu vereinfachen.  In den folgenden Unterabschnitten werden die Änderungen ausführlich beschrieben.  
  
## In diesem Abschnitt  
 [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)  
 Erläutert, wie eine verwaltete `class`, `struct` oder `interface` deklariert wird.  
  
 [Deklaration eines CLR\-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 Erläutert, wie ein Objekt vom Typ Verweisklasse mithilfe eines Trackinghandles deklariert wird.  
  
 [Deklaration eines CLR\-Arrays](../dotnet/declaration-of-a-clr-array.md)  
 Erklärt, wie ein Array deklariert und initialisiert wird.  
  
 [Änderungen in der Initialisierungsreihenfolge für Konstruktoren](../dotnet/changes-in-constructor-initialization-order.md)  
 Erläutert wichtige Änderungen in der Initialisierungsreihenfolge für den Klassenkonstruktor.  
  
 [Änderungen in der Destruktorsemantik](../dotnet/changes-in-destructor-semantics.md)  
 Erläutert die nicht\-deterministische Finalisierung, `Finalize` und `Dispose` im Vergleich, die Auswirkungen auf Verweisobjekte sowie die Verwendung einer expliziten `Finalize`\-Methode.  
  
 **Hinweis:** Die Erläuterung von Delegaten erfolgt erst später im Abschnitt [Delegaten und Ereignisse](../dotnet/delegates-and-events.md), um sie gemeinsam mit Ereignismembern innerhalb einer Klasse, dem Hauptthema in [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md), vorzustellen.  
  
## Siehe auch  
 [Einführung in die C\+\+\/CLI\-Migration](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)
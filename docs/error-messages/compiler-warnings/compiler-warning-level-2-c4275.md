---
title: "Compilerwarnung (Stufe 2) C4275 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4275"
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Compilerwarnung (Stufe 2) C4275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' ist keine DLL\-Schnittstelle und wurde als Basisklasse für die DLL\-Schnittstelle 'Bezeichner' verwendet  
  
 Eine exportierte Klasse wurde von einer Klasse abgeleitet, die nicht exportiert wurde.  
  
 Um die Gefahr einer Datenbeschädigung beim Exportieren einer Klasse mit [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) zu minimieren, stellen Sie Folgendes sicher:  
  
-   Auf alle statischen Daten wird über Funktionen zugegriffen, die aus der DLL exportiert werden.  
  
-   Inlinemethoden der Klasse dürfen statische Daten nicht ändern.  
  
-   Keine Inlinemethoden der Klasse verwenden CRT\-Funktionen, und keine anderen Bibliotheksfunktionen verwenden statische Daten.  
  
-   Keine Inlinemethoden der Klasse verwenden CRT\-Funktionen oder andere Bibliotheksfunktionen, mit denen Sie z. B. auf statische Daten zugreifen.  
  
-   Methoden der Klasse \(unabhängig von Inlining\) dürfen keine Typen verwenden, bei denen die Instanziierung in der EXE und der DLL über verschiedene statische Daten verfügen.  
  
 Sie können das Exportieren von Klassen vermeiden, indem Sie eine DLL definieren, durch die eine Klasse mit virtuellen Funktionen sowie Funktionen definiert werden, die zum Instanziieren und Löschen von Objekten des Typs aufgerufen werden können.  Sie können dann einfach virtuelle Funktionen für den Typ aufrufen.  
  
 Weitere Informationen zum Exportieren von Vorlagen, Sie finden [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4275 kann in Visual C\+\+ ignoriert werden, wenn Sie von einem Typ in der C\+\+\-Standardbibliothek ableiten, eine Debugversion kompilieren \(**\/MTd**\) und sich die Fehlermeldung des Compilers auf "\_Container\_base" bezieht.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```
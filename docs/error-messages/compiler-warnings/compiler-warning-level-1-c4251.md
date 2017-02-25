---
title: "Compilerwarnung (Stufe 1) C4251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4251"
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Compilerwarnung (Stufe 1) C4251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die Klasse 'Typ' benötigt eine DLL\-Schnittstelle, damit Clients der Klasse 'Typ2' sie verwenden können  
  
 Um die Gefahr einer Datenbeschädigung beim Exportieren einer Klasse mit [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) zu minimieren, stellen Sie Folgendes sicher:  
  
-   Auf alle statischen Daten wird über Funktionen zugegriffen, die aus der DLL exportiert werden.  
  
-   Inlinemethoden der Klasse dürfen statische Daten nicht ändern.  
  
-   Keine Inlinemethoden der Klasse verwenden CRT\-Funktionen, und keine anderen Bibliotheksfunktionen verwenden statische Daten \(weitere Informationen finden Sie unter [Potenzielle Fehler bei der Übergabe von CRT\-Objekten über DLL\-Grenzen](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)\).  
  
-   Methoden der Klasse \(unabhängig von Inlining\) dürfen keine Typen verwenden, bei denen die Instanziierung in der EXE und der DLL über verschiedene statische Daten verfügen.  
  
 Sie können das Exportieren von Klassen vermeiden, indem Sie eine DLL definieren, durch die eine Klasse mit virtuellen Funktionen sowie Funktionen definiert werden, die zum Instanziieren und Löschen von Objekten des Typs aufgerufen werden können.  Sie können dann einfach virtuelle Funktionen für den Typ aufrufen.  
  
 Weitere Informationen zum Exportieren von Vorlagen, Sie finden [http:\/\/support.microsoft.com\/default.aspx?scid\=KB;EN\-US;168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4251 kann ignoriert werden, wenn Sie von einem Typ in der C\+\+\-Standardbibliothek ableiten, eine Debugversion kompilieren \(**\/MTd**\) und sich die Fehlermeldung des Compilers auf "\_Container\_base" bezieht.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```
---
title: Compiler &quot;C4275 (Stufe 2)&quot; | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 873a96d4595b75ff6b9567500723c32d7ba5bd2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4275"></a>Compilerwarnung (Stufe 2) C4275
nicht-DLL-Schnittstelle Classkey 'Bezeichner' als Basisklasse verwendet für die DLL-Schnittstelle Klassenschlüssel "Bezeichner"  
  
 Eine exportierte Klasse wurde von einer Klasse abgeleitet, die nicht exportiert wurde.  
  
 Um die Gefahr der Beschädigung von Daten zu minimieren, exportieren Sie eine Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicher, dass:  
  
-   Alle statischen Daten erfolgt über Funktionen, die aus der DLL exportiert werden.  
  
-   Inlinemethoden der Klasse dürfen statische Daten ändern.  
  
-   Inlinemethoden der Klasse verwenden CRT-Funktionen oder andere Bibliotheksfunktionen verwenden statische Daten.  
  
-   Keine Funktionen Inlinemethoden der Klasse verwenden CRT-Funktionen oder andere Bibliotheksfunktionen, z. B. Sie statische auf Daten zugreifen.  
  
-   Keine Methoden der Klasse (unabhängig von inlining) können Typen verwenden, da die Instanziierung in der EXE und DLL statische Daten verfügen.  
  
 Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen sowie Funktionen aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann einfach virtuelle Funktionen für den Typ aufrufen.  
  
 Weitere Informationen zum Exportieren von Vorlagen finden Sie unter [Http://support.microsoft.com/default.aspx?scid=KB; EN-US;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4275 kann in Visual C++ ignoriert werden, wenn Sie von einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```

---
title: Compiler (Stufe 1) C4251 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: b75c3e6c93c0963a692b210b158339ea5e9eacac
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4251"></a>Compilerwarnung (Stufe 1) C4251
'Bezeichner': Klasse 'Typ' Dll-Schnittstelle, die von der Klasse 'Typ2' verwendet werden soll  
  
 Um die Gefahr der Beschädigung von Daten zu minimieren, exportieren Sie eine Klasse mit [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicher, dass:  
  
-   Alle statischen Daten ist der Zugriff über Funktionen, die aus der DLL exportiert werden.  
  
-   Inlinemethoden der Klasse dürfen statische Daten ändern.  
  
-   Inlinemethoden der Klasse verwenden CRT-Funktionen oder andere Bibliotheksfunktionen verwenden statische Daten (finden Sie unter [potenzielle Fehler Übergabe von CRT-Objekten über DLL Grenzen](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) für Weitere Informationen).  
  
-   Keine Methoden der Klasse (unabhängig von inlining) können Typen verwenden, da die Instanziierung in der EXE und DLL statische Daten verfügen.  
  
 Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen sowie Funktionen aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann einfach virtuelle Funktionen für den Typ aufrufen.  
  
 Weitere Informationen zum Exportieren von Vorlagen finden Sie unter [Http://support.microsoft.com/default.aspx?scid=KB; EN-US;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4251 können ignoriert werden, wenn Sie von einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```

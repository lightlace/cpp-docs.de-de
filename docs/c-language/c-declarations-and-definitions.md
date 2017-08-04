---
title: C-Deklarationen und -Definitionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ad61f4fd319c646c704faba7bff40fe263fc3a44
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-declarations-and-definitions"></a>C-Deklarationen und -Definitionen
Eine "Deklaration" erstellt eine Zuordnung zwischen einer bestimmten Variable, einer Funktion oder einem Typ und den zugehörigen Attributen. [Übersicht über Deklarationen](../c-language/overview-of-declarations.md) gibt die ANSI-Syntax für das `declaration`-Nichtterminal an. Eine Deklaration gibt auch an, wo und wann auf einen Bezeichner zugegriffen werden kann (die "Verknüpfung" eines Bezeichners). Weitere Informationen zu Verknüpfungen finden Sie unter [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md).  
  
 Eine Definition einer Variablen erstellt die gleichen Zuordnungen wie eine Deklaration, bewirkt jedoch auch, dass Speicher für die Variable zugeordnet wird.  
  
 Beispielsweise werden `main`-, `find`- und `count`-Funktionen sowie `var`- und `val`-Variablen in einer Quelldatei in dieser Reihenfolge definiert:  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 Die Variablen `var` und `val` können in den Funktionen `find` und `count` verwendet werden; weitere Deklarationen sind nicht erforderlich. Diese Namen sind jedoch in `main` nicht sichtbar (auf sie kann nicht zugegriffen werden).  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)

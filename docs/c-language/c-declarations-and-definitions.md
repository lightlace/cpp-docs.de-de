---
title: C-Deklarationen und -Definitionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c459999ab902a2498d4ffe4cc2d437a0a432b9b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381564"
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
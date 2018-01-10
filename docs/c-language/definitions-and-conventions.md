---
title: Definitionen und Konventionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02a6cc8ffcb5748544191673de8f07e87449e806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="definitions-and-conventions"></a>Definitionen und Konventionen
Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
 Nichtterminale sind Platzhalter in der Syntax und werden an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein.  
  
 Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben. Ein auf ein Objekt angewendeter  
  
```  
  
{  
expression <SUB>opt</SUB> }  
```  
  
 gibt einen optionalen Ausdruck an, der in Klammern eingeschlossen wird.  
  
 Die Syntaxkonventionen verwenden verschiedene Schriftartattribute für unterschiedliche Syntaxkomponenten. Die Symbole und die Schriftarten lauten wie folgt:  
  
|Attribut|description|  
|---------------|-----------------|  
|*nonterminal*|Kursivschrift gibt Nichtterminale an.|  
|**const**|Fett formatierte Terminale sind literale, reservierte Symbole und Wörter, die wie gezeigt eingegeben werden müssen. Bei Zeichen in diesem Kontext wird immer die Groß-/Kleinschreibung beachtet.|  
|opt|Nichtterminale, die von "opt" gefolgt werden, sind immer optional.|  
|Standardschriftart|Zeichen des in dieser Schriftart beschriebenen oder aufgeführten Satzes können als Terminals in C-Anweisungen verwendet werden.|  
  
 Ein Doppelpunkt (**:**) nach einem Nichtterminal führt ihre Definition ein. Alternative Definitionen werden in separaten Zeilen aufgeführt, außer wenn sie mit den Wörtern "one of" eingeleitet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md)
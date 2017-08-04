---
title: Definitionen und Konventionen | Microsoft-Dokumentation
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
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
caps.latest.revision: 6
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
ms.openlocfilehash: fa335f2eec22e6f3008abe49f7ac36308ce0ad9a
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="definitions-and-conventions"></a>Definitionen und Konventionen
Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
 Nichtterminale sind Platzhalter in der Syntax und werden an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein.  
  
 Eine optionale Komponente wird durch das tiefgestellte "opt" angegeben. Beispiel:  
  
```  
  
{  
expression <SUB>opt</SUB> }  
```  
  
 gibt einen optionalen Ausdruck an, der in Klammern eingeschlossen wird.  
  
 Die Syntaxkonventionen verwenden verschiedene Schriftartattribute für unterschiedliche Syntaxkomponenten. Die Symbole und die Schriftarten lauten wie folgt:  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|*nonterminal*|Kursivschrift gibt Nichtterminale an.|  
|**const**|Fett formatierte Terminale sind literale, reservierte Symbole und Wörter, die wie gezeigt eingegeben werden müssen. Bei Zeichen in diesem Kontext wird immer die Groß-/Kleinschreibung beachtet.|  
|opt|Nichtterminale, die von "opt" gefolgt werden, sind immer optional.|  
|Standardschriftart|Zeichen des in dieser Schriftart beschriebenen oder aufgeführten Satzes können als Terminals in C-Anweisungen verwendet werden.|  
  
 Ein Doppelpunkt (**:**) nach einem Nichtterminal führt ihre Definition ein. Alternative Definitionen werden in separaten Zeilen aufgeführt, außer wenn sie mit den Wörtern "one of" eingeleitet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md)

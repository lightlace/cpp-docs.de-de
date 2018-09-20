---
title: Definitionen und Konventionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- nonterminals definition
ms.assetid: f9b3cf5f-6a7c-4a10-9b18-9d4a43efdaeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74a29acfcdc58b068ebabe9bc1c9b033cf801c21
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760405"
---
# <a name="definitions-and-conventions"></a>Definitionen und Konventionen
Bei Terminalen handelt es sich um Endpunkte in einer Syntaxdefinition. Es ist keine andere Auflösung möglich. Terminale enthalten den Satz reservierter Wörter und benutzerdefinierter Bezeichner.  
  
Nichtterminale sind Platzhalter in der Syntax und werden an anderer Stelle in dieser Syntaxzusammenfassung definiert. Definitionen können rekursiv sein.  
  
Eine optionale Komponente wird durch das tiefgestellte <sub>opt</sub> angegeben. Ein auf ein Objekt angewendeter  
  
> **{** *expression*<sub>opt</sub> **}**
  
gibt einen optionalen Ausdruck an, der in Klammern eingeschlossen wird.  
  
Die Syntaxkonventionen verwenden verschiedene Schriftartattribute für unterschiedliche Syntaxkomponenten. Die Symbole und die Schriftarten lauten wie folgt:  
  
|Attribut|Beschreibung |  
|---------------|-----------------|  
|*nonterminal*|Kursivschrift gibt Nichtterminale an.|  
|**const**|Fett formatierte Terminale sind literale, reservierte Symbole und Wörter, die wie gezeigt eingegeben werden müssen. Bei Zeichen in diesem Kontext wird immer die Groß-/Kleinschreibung beachtet.|  
|<sub>opt</sub>|Nichtterminale, auf die <sub>opt</sub> folgt, sind immer optional.|  
|Standardschriftart|Zeichen des in dieser Schriftart beschriebenen oder aufgeführten Satzes können als Terminals in C-Anweisungen verwendet werden.|  
  
Ein Doppelpunkt (**:**) nach einem Nichtterminal führt ihre Definition ein. Alternative Definitionen werden in separaten Zeilen aufgeführt, außer wenn sie mit den Wörtern "one of" eingeleitet werden.  
  
## <a name="see-also"></a>Siehe auch  
[Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md)
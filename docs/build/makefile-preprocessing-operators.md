---
title: Vorverarbeiten von Operatoren Makefile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d2d8aa3d428b45da81b2f9256988e089f121dd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="makefile-preprocessing-operators"></a>Operatoren für den Präprozessorlauf eines Makefiles
Makefile-Vorverarbeitungsausdrücke können Operatoren verwenden, die auf konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade angewendet werden. Zum Auswerten des Ausdrucks erweitert der Präprozessor zuerst Makros, führt dann Befehle aus und führt anschließend die Vorgänge durch. Vorgänge werden in der Reihenfolge der expliziten Gruppierung in Klammern ausgewertet und dann in der Reihenfolge der Operatorrangfolge. Das Ergebnis ist ein konstanter Wert.  
  
 Der Operator `DEFINED` ist ein logischer Operator, der auf einen Makronamen angewendet wird. Der Ausdruck `DEFINED(` *Macroname* `)` ist "true" Wenn *Macroname* definiert ist, auch wenn sie nicht über einen zugewiesenen Wert verfügt. `DEFINED` in Kombination mit `!IF` oder `!ELSE IF` entspricht `!IFDEF` oder `!ELSE IFDEF`. Im Gegensatz zu diesen Direktiven kann `DEFINED` jedoch in komplexen Ausdrücken verwendet werden.  
  
 Der Operator `EXIST` ist ein logischer Operator, der auf einen Dateisystempfad angewendet wird. `EXIST(`*Pfad* `)` ist "true" Wenn *Pfad* vorhanden ist. Das Ergebnis von `EXIST` kann in binären Ausdrücken verwendet werden. Wenn *Pfad* Leerzeichen enthält, müssen Sie ihn in doppelte Anführungszeichen.  
  
 Zum Vergleichen von zwei Zeichenfolgen verwenden Sie den Gleichheitsoperator (`==`) oder den Ungleichheitsoperator (`!=`). Schließen Sie Zeichenfolgen in doppelte Anführungszeichen ein.  
  
 Ganzzahlige Konstanten können die unären Operatoren für numerische Negation (`-`), das Einerkomplement (`~`) und die logische Negation (`!`) verwenden.  
  
 Ausdrücke können die folgenden Operatoren verwenden. Die Operatoren mit gleichem Rang werden zusammengruppiert, und die Gruppen werden absteigender Rangfolge aufgelistet. Unäre Operatoren werden dem Operanden rechts zugeordnet. Binäre Operatoren mit gleichem Rang werden den Operanden von links nach rechts zugeordnet.  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|`DEFINED(`*Macroname*`)`|Produziert einen logischen Wert für den aktuellen definitionszustand von *Macroname*.|  
|`EXIST(`*Pfad*`)`|Produziert einen logischen Wert für die Existenz einer Datei in *Pfad*.|  
|||  
|`!`|Unäres logisches NOT.|  
|`~`|Unäres Einerkomplement.|  
|`-`|Unäre Negation.|  
|||  
|`*`|Multiplikation.|  
|`/`|Division.|  
|`%`|Modul (Rest).|  
|||  
|`+`|Addition.|  
|`-`|Subtraktion.|  
|||  
|`<<`|Bitweise Verschiebung links.|  
|`>>`|Bitweise Verschiebung rechts.|  
|||  
|`<=`|Kleiner oder gleich.|  
|`>=`|Größer oder gleich.|  
|`<`|Kleiner als.|  
|`>`|Größer als.|  
|||  
|`==`|Gleichheit.|  
|`!=`|Ungleichheit.|  
|||  
|`&`|Bitweises AND.|  
|`^`|Bitweises XOR.|  
|`&#124;`|Bitweises OR.|  
|||  
|`&&`|Logisches AND.|  
|||  
|`&#124;&#124;`|Logisches OR.|  
  
> [!NOTE]
>  Der bitweise XOR-Operator (`^`) entspricht dem Escapezeichen und muss mit dem Escapezeichen versehen werden (wie `^^`), wenn er in einem Ausdruck verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke für die Vorverarbeitung eines Makefiles](../build/expressions-in-makefile-preprocessing.md)
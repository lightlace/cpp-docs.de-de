---
title: "Operatoren f&#252;r den Pr&#228;prozessorlauf eines Makefiles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINED-Operator"
  - "EXIST-Operator"
  - "Makefiles, Vorverarbeiten von Operatoren"
  - "NMAKE (Programm), Operatoren"
  - "Operatoren [C++], Makefile-Vorverarbeitung"
  - "Vorverarbeiten von NMAKE-Makefileoperatoren"
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Operatoren f&#252;r den Pr&#228;prozessorlauf eines Makefiles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Makefile\-Vorverarbeitungsausdrücke können Operatoren verwenden, die auf konstante Werte, Exitcodes von Befehlen, Zeichenfolgen, Makros und Dateisystempfade angewendet werden.  Zum Auswerten des Ausdrucks erweitert der Präprozessor zuerst Makros, führt dann Befehle aus und führt anschließend die Vorgänge durch.  Vorgänge werden in der Reihenfolge der expliziten Gruppierung in Klammern ausgewertet und dann in der Reihenfolge der Operatorrangfolge.  Das Ergebnis ist ein konstanter Wert.  
  
 Der Operator `DEFINED` ist ein logischer Operator, der auf einen Makronamen angewendet wird.  Der Ausdruck `DEFINED(`*macroname*`)` ist wahr, wenn *macroname* definiert ist, selbst wenn ihm kein Wert zugewiesen ist.  `DEFINED` in Kombination mit `!IF` oder `!ELSE IF` entspricht `!IFDEF` oder `!ELSE IFDEF`.  Im Gegensatz zu diesen Direktiven kann `DEFINED` jedoch in komplexen Ausdrücken verwendet werden.  
  
 Der Operator `EXIST` ist ein logischer Operator, der auf einen Dateisystempfad angewendet wird.  `EXIST(`*path*`)` ist wahr, wenn *path* existiert.  Das Ergebnis von `EXIST` kann in binären Ausdrücken verwendet werden.  Wenn *path* Leerzeichen enthält, schließen Sie diese in doppelten Anführungszeichen ein.  
  
 Zum Vergleichen von zwei Zeichenfolgen verwenden Sie den Gleichheitsoperator \(`==`\) oder den Ungleichheitsoperator \(`!=`\).  Schließen Sie Zeichenfolgen in doppelte Anführungszeichen ein.  
  
 Ganzzahlige Konstanten können die unären Operatoren für numerische Negation \(`–`\), das Einerkomplement \(`~`\) und die logische Negation \(`!`\) verwenden.  
  
 Ausdrücke können die folgenden Operatoren verwenden.  Die Operatoren mit gleichem Rang werden zusammengruppiert, und die Gruppen werden absteigender Rangfolge aufgelistet.  Unäre Operatoren werden dem Operanden rechts zugeordnet.  Binäre Operatoren mit gleichem Rang werden den Operanden von links nach rechts zugeordnet.  
  
|Operator|Beschreibung|  
|--------------|------------------|  
|`DEFINED(` *macroname* `)`|Produziert einen logischen Wert für den aktuellen Definitionszustand von *macroname*.|  
|`EXIST(` *path* `)`|Produziert einen logischen Wert für die Existenz einer Datei in *path*.|  
|||  
|`!`|Unäres logisches NOT.|  
|`~`|Unäres Einerkomplement.|  
|`-`|Unäre Negation.|  
|||  
|`*`|Multiplikation.|  
|`/`|Division.|  
|`%`|Modul \(Rest\).|  
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
>  Der bitweise XOR\-Operator \(`^`\) entspricht dem Escapezeichen und muss mit dem Escapezeichen versehen werden \(wie `^^`\), wenn er in einem Ausdruck verwendet wird.  
  
## Siehe auch  
 [Ausdrücke für den Präprozessorlauf eines Makefiles](../build/expressions-in-makefile-preprocessing.md)
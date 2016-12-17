---
title: "Un&#228;re arithmetische Operatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "! Operator, Unäre arithmetische Operatoren"
  - "~ (Operator), Einerkomplementoperator"
  - "+-Operator, Unäre Operatoren"
  - "Arithmetische Operatoren [C++], Unär"
  - "bitwise-complement-Operator"
  - "Ausrufezeichen"
  - "Logische Negation"
  - "Operatoren [C], Unär"
  - "Tildeoperator (~) für Einerkomplement"
  - "Unäre Operatoren"
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Un&#228;re arithmetische Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die C\-Operatoren unär, arithmetische Negation, Komplement und logische Negation werden in der folgenden Liste beschrieben:  
  
|Operator|Beschreibung|  
|--------------|------------------|  
|**\+**|Der unäre Plus\-Operator, der einem Ausdruck in Klammern vorangestellt ist, erzwingt die Gruppierung der eingeschlossenen Vorgänge.  Er wird mit Ausdrücken verwendet, die mehr als einen assoziativen oder kommutativen binären Operator beinhalten.  Der Operand muss ein arithmetischer Typ sein.  Das Ergebnis ist der Wert des Operanden.  Ein ganzzahliger Operand unterliegt einer ganzzahligen Erweiterung.  Der Ergebnistyp ist der Typ des höhergestuften Operanden.|  
|**–**|Der arithmetische Negationsoperator erzeugt die Negation \(Zweierkomplement\) seines Operanden.  Der Operand muss ein Ganzzahl\- oder Gleitkommawert sein.  Dieser Operator führt die üblichen arithmetischen Konvertierungen aus.|  
|`~`|Der bitweise Komplementoperator \(oder bitweiser NOT\-Operator\) erzeugt das bitweise Komplement seines Operanden.  Der Operand muss ein Ganzzahltyp sein.  Dieser Operator führt übliche arithmetische Konvertierungen aus. Das Ergebnis hat den Typ des Operanden nach der Konvertierung.|  
|**\!**|Der logische Negations\-Operator \(logischer NOT\-Operator\) erzeugt den Wert 0, wenn sein Operand "true" \(ungleich 0\) ist. Er erzeugt den Wert 1, wenn sein Operand "false" \(0\) ist.  Das Ergebnis ist vom Typ `int`.  Der Operand muss ein Ganzzahl\-, Gleitkomma\- oder Zeigerwert sein.|  
  
 Unäre arithmetische Operationen für Zeiger sind ungültig.  
  
## Beispiele  
 Die folgenden Beispiele veranschaulichen die unären arithmetischen Operatoren:  
  
```  
short x = 987;  
    x = -x;  
```  
  
 Im obigen Beispiel ist der neue Wert von `x` der negative Wert von 987, oder – 987.  
  
```  
unsigned short y = 0xAAAA;  
    y = ~y;  
```  
  
 In diesem Beispiel ist der neue Wert, der `y` zugewiesen wird, das Einerkomplement des Werts ohne Vorzeichen 0xAAAA, oder 0x5555.  
  
```  
if( !(x < y) )  
```  
  
 Wenn `x` größer oder gleich `y` ist, lautet das Ergebnis des Ausdrucks 1 \("true"\).  Wenn `x` kleiner ist als `y`, ist das Ergebnis 0 \("false"\).  
  
## Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)
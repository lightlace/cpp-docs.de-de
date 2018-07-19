---
title: Unäre arithmetische Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07fde5da39034ff180cad5b6678f27fe8252ce10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390367"
---
# <a name="unary-arithmetic-operators"></a>Unäre arithmetische Operatoren
Die C-Operatoren unär, arithmetische Negation, Komplement und logische Negation werden in der folgenden Liste beschrieben:  
  
|Operator|description|  
|--------------|-----------------|  
|**+**|Der unäre Plus-Operator, der einem Ausdruck in Klammern vorangestellt ist, erzwingt die Gruppierung der eingeschlossenen Vorgänge. Er wird mit Ausdrücken verwendet, die mehr als einen assoziativen oder kommutativen binären Operator beinhalten. Der Operand muss ein arithmetischer Typ sein. Das Ergebnis ist der Wert des Operanden. Ein ganzzahliger Operand unterliegt einer ganzzahligen Erweiterung. Der Ergebnistyp ist der Typ des höhergestuften Operanden.|  
|**-**|Der arithmetische Negationsoperator erzeugt die Negation (Zweierkomplement) seines Operanden. Der Operand muss ein Ganzzahl- oder Gleitkommawert sein. Dieser Operator führt die üblichen arithmetischen Konvertierungen aus.|  
|`~`|Der bitweise Komplementoperator (oder bitweiser NOT-Operator) erzeugt das bitweise Komplement seines Operanden. Der Operand muss ein Ganzzahltyp sein. Dieser Operator führt übliche arithmetische Konvertierungen aus. Das Ergebnis hat den Typ des Operanden nach der Konvertierung.|  
|**!**|Der logische Negations-Operator (logischer NOT-Operator) erzeugt den Wert 0, wenn sein Operand TRUE (ungleich 0) ist. Er erzeugt den Wert 1, wenn sein Operand FALSE (0) ist. Das Ergebnis ist vom Typ `int`. Der Operand muss ein Ganzzahl-, Gleitkomma- oder Zeigerwert sein.|  
  
 Unäre arithmetische Operationen für Zeiger sind ungültig.  
  
## <a name="examples"></a>Beispiele  
 Die folgenden Beispiele veranschaulichen die unären arithmetischen Operatoren:  
  
```  
short x = 987;  
    x = -x;  
```  
  
 Im obigen Beispiel ist der neue Wert von `x` der negative Wert von 987, oder -987.  
  
```  
unsigned short y = 0xAAAA;  
    y = ~y;  
```  
  
 In diesem Beispiel ist der neue Wert, der `y` zugewiesen wird, das Einerkomplement des Werts ohne Vorzeichen 0xAAAA, oder 0x5555.  
  
```  
if( !(x < y) )  
```  
  
 Wenn `x` größer oder gleich `y` ist, lautet das Ergebnis des Ausdrucks 1 ("true"). Wenn `x` kleiner ist als `y`, ist das Ergebnis 0 ("false").  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)
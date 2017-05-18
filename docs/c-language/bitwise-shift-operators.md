---
title: Bitweise Schiebeoperatoren | Microsoft-Dokumentation
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
- operators [C++], bitwise
- shift operators, bitwise
- bitwise-shift operators
- operators [C++], shift
ms.assetid: d0485785-5c72-47e1-a7c0-0adde03ade23
caps.latest.revision: 10
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 54cd2dad24563082c820999ff53e17b4d04380f7
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="bitwise-shift-operators"></a>Bitweise Schiebeoperatoren
Die Schiebeoperatoren verschieben ihren ersten Operanden um die Anzahl von Positionen nach links (`<<`) oder rechts (`>>`), wie es durch den zweiten Operanden angegeben wird.  
  
## <a name="syntax"></a>Syntax  
 *shift-expression*:  
 *additive-expression*  
  
 *shift-expression* `<<` *additive-expression shift-expression* `>>` *additive-expression*  
  
 Beide Operanden müssen ganzzahlige Werte sein. Diese Operatoren führen die üblichen arithmetischen Konvertierungen aus. Der Typ des Ergebnisses ist der Typ des linken Operanden nach der Konvertierung.  
  
 Für links gerichtete Verschiebungen sind die frei werdenden rechten Bits auf 0 festgelegt. Für rechts gerichtete Verschiebungen werden die frei werdenden linken Bits anhand des Typs des ersten Operanden nach der Konvertierung gefüllt. Wenn sie vom Typ `unsigned` sind, werden sie auf 0 festgelegt. Andernfalls werden sie mit Kopien des signierten Bits gefüllt. Für Left Shift-Operatoren ohne Überlauf ist die Anweisung  
  
```  
expr1 << expr2   
```  
  
 identisch mit der Multiplikation mit 2<sup>expr2</sup>. Für Right Shift-Operatoren ist  
  
```  
expr1 >> expr2   
```  
  
 identisch mit der Division durch 2<sup>expr2`expr1`, wenn </sup> kein Vorzeichen oder einen nicht negativen Wert hat.  
  
 Das Ergebnis eines Schiebevorgangs ist nicht definiert, wenn der zweite Operand negativ ist oder wenn der rechte Operand größer als oder gleich der Breite des höher gestuften linken Operanden ist (in Bits).  
  
 Da Konvertierungen, die von Schiebeoperatoren ausgeführt werden, keine Überlauf- oder Unterlaufbedingungen vorsehen, gehen Informationen möglicherweise verloren, wenn das Ergebnis eines Schiebevorgangs nach der Konvertierung nicht im Typ des ersten Operanden dargestellt werden kann.  
  
```  
unsigned int x, y, z;  
  
x = 0x00AA;  
y = 0x5500;  
  
z = ( x << 8 ) + ( y >> 8 );  
```  
  
 In diesem Beispiel wird `x` um acht Positionen nach links verschoben und `y` um acht Positionen nach rechts. Die verschobenen Werte werden unter Angabe von 0xAA55 hinzugefügt und dem Wert `z` zugewiesen.  
  
 Das Verschieben eines negativen Werts nach rechts ergibt die Hälfte des ursprünglichen Werts (abgerundet). Beispiel: Die Zahl -253 (Binärzahl 11111111 00000011), die um ein Bit nach rechts verschoben wurde, ergibt -127 (Binärzahl 11111111 10000001). Die positive Zahl "253" wird nach rechts verschoben, um +126 zu erzeugen.  
  
 Durch die Verschiebung nach rechts wird das signierte Bit beibehalten. Wenn eine ganze Zahl mit Vorzeichen nach rechts verschoben wird, bleibt das wichtigste Byte festgelegt. Bei der Rechtsverschiebung einer ganzen Zahl ohne Vorzeichen wird das wichtigste Byte gelöscht.  
  
## <a name="see-also"></a>Siehe auch  
 [Leftshift- und Rightshift-Operatoren (>> und <<)](../cpp/left-shift-and-right-shift-operators-input-and-output.md)

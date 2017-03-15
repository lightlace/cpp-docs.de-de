---
title: "C-Multiplikationsoperatoren | Microsoft Docs"
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
  - "%-Operator"
  - "/-Operator"
  - "/-Operator, Multiplikationsoperatoren"
  - "Arithmetische Operatoren [C++], Multiplikationsoperatoren"
  - "Multiplikationsoperator [C++], Multiplikationsoperatoren"
  - "Operatoren [C], Multiplikation"
  - "Restoperator (%)"
  - "Schrägstrich-Operator (/)"
ms.assetid: 495471c9-319b-4eb4-bd97-039a025fd3a9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C-Multiplikationsoperatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Multiplikationsoperatoren führen Multiplikations\- **\***, Divisions\- \(**\/**\) und Restoperationen \(`%`\) aus.  
  
 **Syntax**  
  
 *multiplicative\-expression*:  
 *cast\-expression*  
  
 *multiplicative\-expression*  **\***  *cast\-expression*  
  
 *multiplicative\-expression*  **\/**  *cast\-expression*  
  
 *multiplicative\-expression*  **%**  *cast\-expression*  
  
 Die Operanden des Restoperators \(`%`\) müssen ganzzahlig sein.  Die Operatoren der Multiplikation \(**\***\) und der Division \(**\/**\) können Operanden vom Typ Ganzzahl, Gleitkomma oder Zeiger akzeptieren. Dabei können sich die Operandentypen unterscheiden.  
  
 Die multiplikativen Operatoren führen die üblichen arithmetischen Konvertierungen für die Operanden aus.  Der Ergebnistyp ist der Typ der Operanden nach der Konvertierung.  
  
> [!NOTE]
>  Da Konvertierungen, die von den Multiplikationsoperatoren ausgeführt werden, keine Überlauf\- oder Unterlaufbedingungen vorsehen, gehen Informationen möglicherweise verloren, wenn das Ergebnis eines Multiplikationsvorgangs nach der Konvertierung nicht im Typ der Operanden dargestellt werden kann.  
  
 Die multiplikativen C\-Operatoren sind im Folgenden beschrieben:  
  
|Operator|Beschreibung|  
|--------------|------------------|  
|**\***|Der multiplikative C\-Operator bewirkt die Multiplizierung seiner beiden Operanden.|  
|**\/**|Der Divisionsoperator bewirkt, dass der erste Operanden durch den zweiten geteilt wird.  Wenn zwei ganzzahlige Operanden dividiert werden und das Ergebnis keine ganze Zahl ist, wird sie gemäß den folgenden Regeln gekürzt:|  
||-   Das Ergebnis der Division durch 0 \(null\) ist entsprechend dem ANSI C\-Standard nicht definiert.  Der Microsoft C\-Compiler generiert einen Fehler zur Kompilierzeit oder Laufzeit.|  
||-   Wenn beide Operanden positiv oder ohne Vorzeichen sind, wird das Ergebnis in Richtung 0 abgeschnitten.|  
||-   Wenn einer der beiden Operanden negativ ist, ist es von der Implementierung abhängig, ob das Ergebnis der Operation die größte ganze Zahl kleiner oder gleich dem algebraischen Quotienten oder die kleinste ganze Zahl größer oder gleich dem algebraischen Quotienten ist. \(Weitere Informationen finden Sie im Microsoft\-spezifischen Abschnitt weiter unten.\)|  
|`%`|Das Ergebnis des Restoperators ist das Restergebnis, nachdem der erste Operand durch den zweiten Operanden geteilt wurde.  Wenn die Division ungenau ist, wird das Ergebnis durch die folgenden Regeln bestimmt:|  
||-   Wenn der rechte Operand 0 \(null\) ist, ist das Ergebnis nicht definiert.|  
||-   Wenn beide Operanden positiv oder ohne Vorzeichen sind, ist das Ergebnis positiv.|  
||-   Wenn einer der beiden Operanden negativ und das Ergebnis ungenau ist, ist das Ergebnis von der Implementierung abhängig. \(Weitere Informationen finden Sie im Microsoft\-spezifischen Abschnitt weiter unten.\)|  
  
 **Microsoft\-spezifisch**  
  
 In der Division, in der jeder Operand negativ ist, wird in Richtung 0 abgeschnitten.  
  
 Wenn eine Division mit dem Restoperator negativ ist, hat das Ergebnis dasselbe Vorzeichen wie der Dividend \(der erste Operand im Ausdruck\).  
  
 **END Microsoft\-spezifisch**  
  
## Beispiele  
 Die Deklarationen, die unten dargestellt werden, werden für die folgenden Beispiele verwendet:  
  
```  
int i = 10, j = 3, n;  
double x = 2.0, y;  
```  
  
 Diese Anweisung verwendet den Multiplikationsoperator:  
  
```  
y = x * i;  
```  
  
 In diesem Fall wird `x` mit `i` multipliziert, um den Wert 20.0 zu erhalten.  Das Ergebnis ist vom Typ **double**.  
  
```  
n = i / j;  
```  
  
 In diesem Beispiel wird 10 durch 3 geteilt.  Das Ergebnis wird in Richtung 0 verkürzt, was den Ganzzahlwert 3 liefert.  
  
```  
n = i % j;  
```  
  
 Diese Anweisung weist `n` den ganzzahligen Rest 1 zu, wenn 10 durch 3 dividiert wird.  
  
 **Microsoft\-spezifisch**  
  
 Das Zeichen für den Rest entspricht dem Zeichen des Divisors.  Beispiel:  
  
```  
50 % -6 = 2  
-50 % 6 = -2  
```  
  
 In jedem Fall haben `50` und `2` dasselbe Zeichen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Multiplikationsoperatoren und der Modulus\-Operator](../cpp/multiplicative-operators-and-the-modulus-operator.md)
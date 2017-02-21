---
title: "C-Gleitkommakonstanten | Microsoft Docs"
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
  - "Konstanten, Gleitkomma"
  - "double-Datentyp, Gleitkommakonstanten"
  - "Gleitkommakonstanten"
  - "Gleitkommakonstanten, Informationen über Gleitkommakonstanten"
  - "Gleitkommazahlen, Gleitkommakonstanten"
  - "Typen [C], Konstanten"
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# C-Gleitkommakonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine "Gleitkommakonstante" ist eine Dezimalzahl, die eine reelle Zahl mit Vorzeichen darstellt.  Die Darstellung einer reellen Zahl mit Vorzeichen enthält einen Ganzzahlbereich, einen Teil mit Bruchzahlen und einen Exponenten.  Verwenden Sie Gleitkommakonstanten zum Darstellen von unveränderbaren Gleitkommawerten.  
  
## Syntax  
 *floating\-point\-constant*:  
 *fractional\-constant exponent\-part*  opt *floating\-suffix* opt  
  
 *digit\-sequence exponent\-part floating\-suffix*  opt  
  
 *fractional\-constant*:  
 *digit\-sequence*  opt **.** *digit\-sequence*  
  
 *digit\-sequence*  **.**  
  
 *exponent\-part*:  
 **e**  *sign*  opt *digit\-sequence*  
  
 **E**  *sign*  opt *digit\-sequence*  
  
 *Vorzeichen* : eins der folgenden  
 **\+ –**  
  
 *digit\-sequence*:  
 *digit*  
  
 *digit\-sequence\-Stelle*  
  
 *floating\-suffix* : eins der Folgenden  
 **f l F L**  
  
 Sie können entweder die Stellen vor dem Dezimaltrennzeichen \(der ganzzahlige Teil des Werts\) oder die Stellen nach dem Dezimaltrennzeichen \(der Bruchteil\) auslassen, aber nicht Beides.  Sie können das Dezimaltrennzeichen nur dann weglassen, wenn Sie einen Exponenten einschließen.  Die Ziffern oder Zeichen der Konstante können nicht durch Leerzeichen getrennt werden.  
  
 In den folgenden Beispielen werden einige Formen von Gleitkommakonstanten und Ausdrücken veranschaulicht:  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 Gleitkommakonstanten sind positiv, es sei denn, ihnen wird ein Minuszeichen \(**–**\) vorangestellt.  In diesem Fall wird das Minuszeichen als unärer arithmetischer Negationsoperator behandelt.  Gleitkommakonstanten weisen den Typ **float**, **double** oder `long double` auf.  
  
 Eine Gleitkommakonstante ohne **f**, **F**, **l** oder **L**\-Suffix ist vom Typ **double**.  Wenn der Buchstabe **f** oder **F** als Suffix verwendet wird, ist die Konstante vom Typ **float**.  Mit dem Suffix **l** oder **L** ist sie vom Typ `long double`.  Beispiel:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Beachten Sie, dass beim Microsoft C\-Compiler **long double** dem Typ **double** zuordnet wird.  Weitere Informationen über die Typen **double**, **float** und **long** finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).  
  
 Wie in den folgenden Beispielen veranschaulicht, ist es möglich, den ganzzahligen Teil der Gleitkommakonstante auszulassen.  Die Zahl .75 kann auf unterschiedliche Weise ausgedrückt werden, z. B. wie folgt:  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## Siehe auch  
 [C\-Konstanten](../c-language/c-constants.md)
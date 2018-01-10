---
title: C-Gleitkommakonstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67883acbb2a6d5c0df075c47b7eda0d40a568f38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="c-floating-point-constants"></a>C-Gleitkommakonstanten
Eine "Gleitkommakonstante" ist eine Dezimalzahl, die eine reelle Zahl mit Vorzeichen darstellt. Die Darstellung einer reellen Zahl mit Vorzeichen enthält einen Ganzzahlbereich, einen Teil mit Bruchzahlen und einen Exponenten. Verwenden Sie Gleitkommakonstanten zum Darstellen von unveränderbaren Gleitkommawerten.  
  
## <a name="syntax"></a>Syntax  
 *floating-point-constant*:  
 &nbsp;&nbsp; *fractional-constant exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub>  
 &nbsp;&nbsp; *digit-sequence exponent-part floating-suffix*<sub>opt</sub>  
  
 *fractional-constant*:  
 &nbsp;&nbsp; *digit-sequence*<sub>opt</sub> **.** *digit-sequence*  
 &nbsp;&nbsp; *digit-sequence*  **.**  
  
 *exponent-part*:  
 &nbsp;&nbsp; **e**  *sign*<sub>opt</sub> *digit-sequence*  
 &nbsp;&nbsp; **E**  *sign*<sub>opt</sub> *digit-sequence*  
  
 *sign* : eins der folgenden Zeichen  
 &nbsp;&nbsp; **+ -**  
  
 *digit-sequence*:  
 &nbsp;&nbsp; *digit*  
 &nbsp;&nbsp; *digit-sequence digit*  
  
 *floating-suffix* : eins der folgenden Zeichen  
 &nbsp;&nbsp; **f l F L**  
  
 Sie können entweder die Stellen vor dem Dezimaltrennzeichen (der ganzzahlige Teil des Werts) oder die Stellen nach dem Dezimaltrennzeichen (der Bruchteil) auslassen, aber nicht Beides. Sie können das Dezimaltrennzeichen nur dann weglassen, wenn Sie einen Exponenten einschließen. Die Ziffern oder Zeichen der Konstante können nicht durch Leerzeichen getrennt werden.  
  
 In den folgenden Beispielen werden einige Formen von Gleitkommakonstanten und Ausdrücken veranschaulicht:  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 Gleitkommakonstanten sind positiv, es sei denn, ihnen wird ein Minuszeichen (**-**) vorangestellt. In diesem Fall wird das Minuszeichen als unärer arithmetischer Negationsoperator behandelt. Gleitkommakonstanten weisen den Typ `float`, `double` oder `long double` auf.  
  
 Eine Gleitkommakonstante ohne das Suffix **f**, **F**, **l** oder **L** ist vom Typ `double`. Wenn der Buchstabe **f** oder **F** als Suffix verwendet wird, ist die Konstante vom Typ `float`. Mit dem Suffix **l** oder **L** ist sie vom Typ `long double`. Zum Beispiel:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Beachten Sie, dass der Microsoft C-Compiler `long double` intern genauso darstellt wie den Typ `double`. Weitere Informationen über die Typen `double`, `float` und `long double` finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md).  
  
 Wie in den folgenden Beispielen veranschaulicht, ist es möglich, den ganzzahligen Teil der Gleitkommakonstante auszulassen. Die Zahl .75 kann auf unterschiedliche Weise ausgedrückt werden, z. B. wie folgt:  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C-Konstanten](../c-language/c-constants.md)
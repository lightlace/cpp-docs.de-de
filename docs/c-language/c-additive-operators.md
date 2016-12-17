---
title: "C-Operatoren (additiv)"
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
  - "+-Operator, Additive Operatoren"
  - "Additive Operatoren"
  - "Arithmetische Operatoren [C++], Additive Operatoren"
  - "Operatoren [C], Addition"
  - "Übliche arithmetische Konvertierungen"
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# C-Operatoren (additiv)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Addition\-Operatoren führen Additionen \(**\+**\) und Subtraktionen aus \(**–**\).  
  
## Syntax  
 *additive\-expression*:  
 *multiplicative\-expression*  
  
 *additive\-expression*  **\+**  *multiplicative\-expression*  
  
 *additive\-expression*  **–**  *multiplicative\-expression*  
  
> [!NOTE]
>  Obwohl die Syntax für *additive\-expression* auch *multiplicative\-expression* enthält, heißt das nicht, dass Ausdrücke erforderlich sind, die Multiplikation verwenden.  In der [Zusammenfassung der C\-Sprachsyntax](../c-language/c-language-syntax-summary.md) finden Sie weitere Informationen über die Syntax für *multiplicative\-expression*, *cast\-expression* und *unary\-expression*.  
  
 Die Operanden können Ganzzahl\- oder Gleitkommawerte sein.  Einige Additionsvorgänge können auch auf Zeigerwerten ausgeführt werden, wie in der Erläuterung für die einzelnen Operatoren dargelegt wird.  
  
 Additive Operatoren führen die üblichen arithmetischen Konvertierungen in Operanden vom Typ "integral" oder "floating" aus.  Der Ergebnistyp ist der Typ der Operanden nach der Konvertierung.  Da Konvertierungen, die von den Addition\-Operatoren ausgeführt werden, keine Überlauf\- oder Unterlaufbedingungen vorsehen, gehen Informationen möglicherweise verloren, wenn das Ergebnis eines Additionsvorgangs nach der Konvertierung nicht im Typ der Operanden dargestellt werden kann.  
  
## Siehe auch  
 [Additive Operatoren: \+ und \-](../cpp/additive-operators-plus-and.md)
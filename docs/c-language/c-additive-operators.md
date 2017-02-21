---
title: "C-Operatoren (additiv) | Microsoft Docs"
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
  - "+-Operator, Additive Operatoren"
  - "Additive Operatoren"
  - "Arithmetische Operatoren [C++], Additive Operatoren"
  - "Operatoren [C], Addition"
  - "Übliche arithmetische Konvertierungen"
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
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
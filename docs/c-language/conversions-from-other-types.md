---
title: "Konvertierungen von anderen Typen"
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
  - "Typumwandlungen, Konvertierung"
  - "Werte, Konvertieren"
ms.assetid: 30fbd974-8f5a-4b70-ac44-d3937b96b702
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Konvertierungen von anderen Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da ein `enum`\-Wert definitionsgemäß ein `int`\-Wert ist, sind Konvertierungen aus und in einen `enum`\-Wert identisch mit denen für den Typ `int`.  Für den Microsoft C\-Compiler entspricht eine Ganzzahl **long**.  
  
 **Microsoft\-spezifisch**  
  
 Es sind keine Konvertierungen zwischen Struktur\- oder Union\-Typen zulässig.  
  
 Jeder Wert kann in den Typ `void` konvertiert werden, aber das Ergebnis einer solchen Konvertierung kann nur in einem Kontext verwendet werden, in dem ein Ausdruckswert verworfen wird, z. B. in einer Ausdrucksanweisung.  
  
 Der `void`\-Typ hat definitionsgemäß keinen Wert.  Daher kann er nicht in einen anderen Typ konvertiert werden, und andere Typen können nicht durch Zuweisung in `void` konvertiert werden.  Sie können jedoch explizit einen Wert in den Typ `void` umwandeln, wie in [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md) erläutert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Zuweisungskonvertierungen](../c-language/assignment-conversions.md)
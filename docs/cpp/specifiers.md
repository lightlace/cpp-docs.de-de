---
title: "Spezifizierer"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklarationsspezifizierer"
  - "Deklarationen, Bezeichner"
  - "Bezeichner, In Deklarationen"
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Spezifizierer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird die *decl\-specifiers*\-Komponente \(Deklarationsspezifizierer\) einer [Deklaration](../misc/declarations.md) beschrieben.  
  
 Die folgenden Platzhalter und Sprachschlüsselwörter sind Deklarationsbezeichner:  
  
 *storage\-class\-specifier*  
  
 *type\-specifier*  
  
 *function\-specifier*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [Typedef](assetId:///cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [\_\_declspec](../cpp/declspec.md) `(` *extended\-decl\-modifier\-seq* `)`  
  
## Hinweise  
 Der *decl\-specifiers*\-Teil einer Deklaration ist die längste Sequenz von *decl\-specifiers*, der als Typname verstanden werden kann, ohne dass Zeiger oder Verweismodifizierer enthalten sind.  Der Rest der Deklaration ist der *Deklarator*, der den eingeführten Namen enthält.  
  
 Die folgende Tabelle enthält vier Deklarationen. Sie führt dann die *decl\-specifers*\- und *declarator*\-Komponenten für jede Deklaration getrennt auf.  
  
|Deklaration|*decl\-specifiers*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Da `signed`, `unsigned`, `long` und `short` alle `int` implizieren, wird ein `typedef`\-Name, der auf eines dieser Schlüsselwörter folgt, für einen Member von *declarator\-list* und nicht von *decl\-specifiers* gehalten.  
  
> [!NOTE]
>  Da ein Name neu deklariert werden kann, unterliegt seine Interpretation der letzten Deklaration im aktuellen Gültigkeitsbereich.  Eine Neudeklaration kann beeinflussen, wie Namen vom Compiler interpretiert werden, insbesondere `typedef`\-Namen.  
  
## Siehe auch  
 [Deklarationen](../misc/declarations.md)
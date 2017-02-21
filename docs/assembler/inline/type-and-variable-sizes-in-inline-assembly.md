---
title: "Typen- und Variablengr&#246;&#223;en in der Inlineassembly | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "length"
  - "Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlineassembly, Operatoren"
  - "LENGTH-Operator"
  - "Größe"
  - "SIZE-Operator"
  - "Größe, Abrufen in der Inlineassembly"
  - "TYPE-Operator"
  - "Variablen, Länge"
  - "Variablen, Größe"
  - "Variablen, Typ"
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Typen- und Variablengr&#246;&#223;en in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die **LENGTH**, **SIZE**und TYPE\-Operatoren haben eine endliche Bedeutung in der Inlineassembly.  Sie können nicht an allen mit dem `DUP`\-Operator verwendet werden \(da Sie Daten mit MASM\-Direktiven \- Operatoren oder nicht definiert\).  Aber Sie können sie verwenden, um die Größe von C\- oder C\+\+\-Variablen oder \- Typen:  
  
-   Der **LENGTH**\-Operator kann die Anzahl der Elemente in einem Array zurückgeben.  Es gibt den Wert 1 für Nicht Array von Variablen zurück.  
  
-   Der **SIZE**\-Operator kann die Größe von eine oder C\+\+\-Variable zurückgeben.  Die Größe einer Variablen ist das Produkt aus den **LENGTH** und TYPE.  
  
-   Der TYPE\-Operator kann die Größe von C oder C\+\+\-Typ oder \- Variable zurückzugeben.  Wenn die Variable ein Array ist, gibt TYPE die Größe eines einzelnen Elemente des Arrays zurück.  
  
 Wenn z. B. das Programm das `int` Array mit 8 Elementen verfügt.  
  
```  
int arr[8];  
```  
  
 folgenden Ausdrücke die Assembly C und führen die Größe von `arr` und ihren Elementen.  
  
|\_\_asm|C|Größe|  
|-------------|-------|-----------|  
|**LENGTH** arr|`sizeof`\(arr\)\/`sizeof`\(arr \[0\]\)|8|  
|**SIZE** arr|`sizeof`\(arr\)|32|  
|TYPE\- arr|`sizeof`\(arr \[0\]\)|4|  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)
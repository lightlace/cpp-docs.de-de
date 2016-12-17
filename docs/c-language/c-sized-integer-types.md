---
title: "C-Ganzzahltypen (angepasst)"
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
  - "Angepasste Ganzzahltypen"
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# C-Ganzzahltypen (angepasst)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Microsoft C bietet Unterstützung für ganzzahlige Typen mit angegebener Größe.  Sie können 8\-, 16\-, 32\- oder 64\-Bit\-Ganzzahl\-Variablen deklarieren, indem Sie den \_\_int*n*\-Typbezeichner verwenden, wobei *n* die Größe der ganzzahligen Variable \(in Bit\) ist.  Der Wert von *n* kann 8, 16, 32 oder 64 sein.  Im folgenden Beispiel wird eine Variable für jeden der vier Typen der nach Größe angepassten Ganzzahlen deklariert:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Die ersten drei Typen der nach Größe angepassten Ganzzahlen sind Synonyme für die ANSI\-Typen, die die gleichen Größe haben und nützlich für das Schreiben von übertragbarem Code sind, der sich auf vielen verschiedenen Plattformen genau gleich verhält.  Beachten Sie, dass der \_\_int8\-Datentyp mit dem Typ "char" synonym ist, \_\_int16 mit dem Typ "short" synonym ist und \_\_int32 mit dem Typ "int" synonym ist.  Der \_\_int64\-Typ verfügt über keine äquivalente ANSI\-Entsprechung.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md)
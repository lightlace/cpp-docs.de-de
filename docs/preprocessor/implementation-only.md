---
title: "implementation_only | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "implementation_only"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "implementation_only-Attribut"
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# implementation_only
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Unterdrückt die Generierung der TLH\-Headerdatei \(die primäre Headerdatei\).  
  
## Syntax  
  
```  
implementation_only  
```  
  
## Hinweise  
 Diese Datei enthält alle Deklarationen, die verwendet werden, um den Inhalt der Typbibliothek verfügbar zu machen.  Die TLI\-Headerdatei wird mit den implementierten Wrappermemberfunktionen generiert und in die Kompilierung aufgenommen.  
  
 Wenn dieses Attribut festgelegt ist, befindet sich der Inhalt des TLI\-Headers im selben Namespace wie der, der normalerweise im TLH\-Header verwendet wird.  Außerdem werden die Memberfunktionen nicht als Inline deklariert.  
  
 Das Attribut `implementation_only` ist für die Verwendung mit dem Attribut [no\_implementation](../preprocessor/no-implementation.md) vorgesehen, damit die Implementierungen nicht in die vorkompilierte PCH\-Headerdatei aufgenommen werden.  Eine `#import`\-Anweisung mit dem Attribut `no_implementation` wird in den Quellbereich eingefügt, der verwendet wird, um die PCH zu erstellen.  Die resultierende PCH wird von mehreren Quelldateien verwendet.  Eine `#import`\-Anweisung mit dem Attribut `implementation_only` wird dann außerhalb des PCH\-Bereichs verwendet.  Sie müssen diese Anweisung nur einmal in einer der Quelldateien verwenden.  Dadurch werden alle erforderlichen Wrappermemberfunktionen generiert, ohne dass eine zusätzliche Neukompilierung für jede Quelldatei erforderlich ist.  
  
> [!NOTE]
>  Das Attribut `implementation_only` in einer `#import`\-Anweisung muss zusammen mit einer anderen `#import`\-Anweisung \(derselben Typbibliothek\) mit dem Attribut `no_implementation` verwendet werden.  Andernfalls werden Compilerfehler generiert.  Dies liegt daran, dass die Wrapperklassendefinitionen, die durch die `#import`\-Anweisung mit dem Attribut `no_implementation` generiert werden, erforderlich sind, die Implementierungen zu kompilieren, die vom Attribut `implementation_only` generiert werden.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)
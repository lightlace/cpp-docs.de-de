---
title: "virtual (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "virtual_cpp"
  - "virtual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Basisklassen, Virtuell"
  - "Virtuelle Basisklassen, Deklarieren"
  - "Virtuelle Funktionen, Deklarieren"
  - "virtual-Schlüsselwort [C++]"
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# virtual (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `virtual`\-Schlüsselwort deklariert eine virtuelle Funktion oder eine virtuelle Basisklasse.  
  
## Syntax  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### Parameter  
 `type-specifiers`  
 Gibt den Rückgabetyp der virtuellen Memberfunktion an.  
  
 `member-function-declarator`  
 Deklariert eine Memberfunktion.  
  
 `access-specifier`  
 Definiert die Ebene des Zugriffs auf die Basisklasse, `public`, `protected` oder `private`.  Kann vor oder nach dem `virtual`\-Schlüsselwort angezeigt werden.  
  
 `base-class-name`  
 Identifiziert einen zuvor deklarierten Klassentyp.  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Virtuelle Funktionen](../cpp/virtual-functions.md) und [Virtuelle Basisklassen](../misc/virtual-base-classes.md).  
  
 Siehe auch folgende Schlüsselwörter: [class](../cpp/class-cpp.md), [private](../cpp/private-cpp.md), [public](../cpp/public-cpp.md) und [protected](../cpp/protected-cpp.md).  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)
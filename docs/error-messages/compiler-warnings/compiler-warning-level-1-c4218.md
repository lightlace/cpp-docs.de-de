---
title: "Compilerwarnung (Stufe 1) C4218 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4218"
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Mindestens Angabe einer Speicherklasse oder eines Typs erforderlich  
  
 Bei Verwendung der Microsoft\-Standarderweiterungen \(**\/Ze**\) können Sie eine Variable ohne Angabe eines Typs oder einer Speicherklasse deklarieren.  Der Standardtyp lautet `int`.  
  
## Beispiel  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 Derartige Deklarationen sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.
---
title: "Compilerwarnung (Stufe 4) C4211"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4211"
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Neudefinition von extern als statisch  
  
 Bei Verwendung der Microsoft\-Standarderweiterungen \(**\/Ze**\) können Sie einen `extern`\-Bezeichner neu als **static** definieren.  
  
## Beispiel  
  
```  
// C4211.c  
// compile with: /W4  
extern int i;  
static int i;   // C4211  
  
int main()  
{  
}  
```  
  
 Derartige Neudefinitionen sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.  
  
## Siehe auch  
 [\(NOTINBUILD\)Static Storage\-Class Specifiers](assetId:///3ba9289a-a412-4a17-b319-ceb2c087df48)
---
title: "Compilerwarnung (Stufe 4) C4001 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4001"
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dem Standard nicht entsprechende Erweiterung "einzeiliger Kommentar" wurde verwendet  
  
 Einzeilige Kommentare werden in C\+\+ standardmäßig verwendet, sind in C jedoch kein Standard.  Gemäß strikter ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) wird bei C\-Dateien mit einzeiligen Kommentaren die Warnung C4001 ausgegeben, da eine nicht standardmäßige Erweiterung verwendet wird.  Da einzeilige Kommentare in C\+\+ dem Standard entsprechen, wird beim Kompilieren von C\-Dateien mit einzeiligen Kommentaren bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\) keine C4001\-Warnung ausgegeben.  
  
## Beispiel  
 Um die Warnung zu deaktivieren, kommentieren Sie [\#pragma warning\(disable:4001\)](../../preprocessor/warning.md) aus.  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```
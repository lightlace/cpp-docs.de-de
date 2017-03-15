---
title: "Compilerwarnung (Stufe 4) C4214 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4214"
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Basistyp für Bitfeld ist nicht int  
  
 Bei Verwendung der Microsoft\-Standarderweiterungen \(**\/Ze**\) können Bitfeld\-Strukturmember einen beliebigen ganzzahligen Typ aufweisen.  
  
## Beispiel  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 Derartige Bitfelder sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.
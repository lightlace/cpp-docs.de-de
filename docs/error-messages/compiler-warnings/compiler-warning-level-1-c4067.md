---
title: "Compilerwarnung (Stufe 1) C4067 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4067"
ms.assetid: 1d10353e-8cd5-4b01-9184-a06189b965a4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartete Symbole nach Präprozessordirektive \- Zeilenvorschub erwartet  
  
 Der Compiler hat zusätzliche Zeichen hinter einer Präprozessordirektive gefunden und ignoriert.  Diese Warnung wird nur bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ausgegeben.  
  
```  
// C4067a.cpp  
// compile with: /DX /Za /W1  
#pragma warning(default:4067)  
#if defined(X)  
#else  
#endif v   // C4067  
int main()  
{  
}  
```  
  
### Führen Sie zur Beseitigung dieser Warnung einen der folgenden Schritte durch:  
  
1.  Kompilieren Sie mit **\/Ze**.  
  
2.  Verwenden Sie Kommentartrennzeichen:  
  
```  
// C4067b.cpp  
// compile with: /DX /Za /W1  
#if defined(X)  
#else  
#endif  
int main()  
{  
}  
```
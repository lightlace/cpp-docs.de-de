---
title: "Compilerwarnung (Stufe 2) C4285 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4285"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4285"
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 2) C4285
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rückgabetyp für identifier::operator '\-\>' ist rekursiv, wenn mit Infix\-Notation verwendet  
  
 Die angegebene **operator–\>\(\)**\-Funktion kann den Typ, für den oder definiert wird, ein Verweis auf den Typ zurückgeben, für den sie definiert wurde.  
  
 Im folgenden Beispiel wird C4285 generiert:  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```
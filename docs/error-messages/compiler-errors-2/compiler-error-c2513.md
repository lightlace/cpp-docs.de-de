---
title: "Compilerfehler C2513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2513"
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Keine Variable vor '\=' deklariert  
  
 Der Typspezifizierer steht in einer Deklaration, die keinen Variablenbezeichner enthält.  
  
 Im folgenden Beispiel wird C2513 generiert:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: Initialisierungen einer `typedef` sind nicht mehr zulässig.  Die Initialisierung einer `typedef` ist gemäß Standard nicht zulässig und verursacht jetzt einen Compilerfehler.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Als Alternative könnte `typedef` gelöscht werden, um eine Variable mit einer Aggregatinitialisiererliste zu definieren. Dies ist jedoch nicht empfehlenswert, da hierdurch eine Variable mit demselben Namen des Typs erstellt und der Typname versteckt wird.
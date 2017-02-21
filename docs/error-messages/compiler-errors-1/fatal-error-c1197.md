---
title: "Schwerwiegender Fehler C1197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1197"
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf 'mscorlib.dll\_1' kann nicht verwiesen werden, da das Programm bereits auf 'mscorlib.dll\_2' verweist.  
  
 Der Compiler wird an eine Version von Common Language Runtime angepasst.  Es wurde jedoch der Versuch unternommen, von einer vorherigen Version auf eine Version einer Common Language Runtime\-Datei zu verweisen.  
  
 Zur Behebung des Problems referenzieren Sie Dateien nur von der Version von Common Language Runtime, die im Lieferumfang der Version von Visual C\+\+ enthalten ist, mit der Sie kompilieren.  
  
## Beispiel  
 Im folgenden Beispiel wird C1197 generiert:  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```
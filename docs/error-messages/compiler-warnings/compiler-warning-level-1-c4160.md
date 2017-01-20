---
title: "Compilerwarnung (Stufe 1) C4160"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4160"
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\#pragma**   
 ***pragma* \(pop,...\): Konnte den zuvor per push abgelegten Bezeichner „**   
 ***identifier* “ nicht finden.**  
  
 Eine Pragma\-Anweisung im Quellcode versucht, einen Bezeichner per Pop auszulesen, der nicht per Push veröffentlicht wurde. Um diese Warnung zu vermeiden, achten Sie darauf, dass der ausgelesene Bezeichner ordnungsgemäß gepusht wurde.  
  
 Im folgenden Beispiel wird der Fehler C4160 generiert:  
  
```  
// C4160.cpp // compile with: /W1 #pragma pack(push) #pragma pack(pop, id)   // C4160 // use identifier when pushing to resolve the warning // #pragma pack(push, id) int main() { }  
```
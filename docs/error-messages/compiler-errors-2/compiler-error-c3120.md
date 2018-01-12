---
title: Compilerfehler Fehler C3120 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3120
dev_langs: C++
helpviewer_keywords: C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f52809bca6ddc4672e8206822071f91c62c7009e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3120"></a>Compilerfehler Fehler C3120
"keine Variablenargumentlisten verwenden": Schnittstellenmethoden keine Liste variabler Argumente akzeptiert  
  
 Eine Schnittstellenmethode akzeptiert keine Liste variabler Argumente. Die folgende Schnittstellendefinition wird z. B. C3120 generiert:  
  
```  
// C3120.cpp  
__interface A {  
int X(int i, ...);    // C3120  
};  
  
int main(void) { return(0); }  
```
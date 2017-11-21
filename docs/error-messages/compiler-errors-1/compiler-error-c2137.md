---
title: Compilerfehler C2137 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2137
dev_langs: C++
helpviewer_keywords: C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81cb3b0f227db9093f64b5f5af4aadf5ee45baa1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2137"></a>Compilerfehler C2137
leere Zeichenkonstante  
  
 Die leere Zeichenkonstante (' ') ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2137 generiert:  
  
```  
// C2137.cpp  
int main() {  
   char c = '';   // C2137  
   char d = ' ';   // OK  
}  
```
---
title: Compilerfehler Fehler C2619 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2619
dev_langs:
- C++
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a4ef72e986aae1746444b434997755a260d715ed
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2619"></a>Compilerfehler Fehler C2619
„identifier“: Ein statisches Datenmember ist in einer anonymen Struktur oder Union nicht zulässig.  
  
 Ein Member einer anonymen Struktur oder Union ist als `static` deklariert.  
  
 Im folgenden Beispiel wird C2619 generiert und veranschaulicht, wie Sie diesen Fehler beheben, indem Sie das statische-Schlüsselwort entfernen.  
  
```  
// C2619.cpp  
int main() {  
   union { static int j; };  // C2619  
   union { int j; };  // OK  
}  
```

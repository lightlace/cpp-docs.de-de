---
title: Compilerfehler Fehler C2619 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2619
dev_langs:
- C++
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05f02026dac06647a8fda1eeb7e67cc3eaa586b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
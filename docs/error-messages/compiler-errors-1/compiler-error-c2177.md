---
title: Compilerfehler C2177 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2177
dev_langs:
- C++
helpviewer_keywords:
- C2177
ms.assetid: 2a39a880-cddb-4d3e-a572-645a14c4c478
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 66a9e81f68e7857d12ccf31a00b18791653a0eba
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2177"></a>Compilerfehler C2177
Konstante zu groß  
  
 Ein konstanter Wert ist zu groß für den Variablentyp, dem er zugewiesen ist.  
  
 Im folgenden Beispiel wird C2177 generiert:  
  
```  
// C2177.cpp  
int main() {  
   int a=18446744073709551616;   // C2177  
   int b=18446744073709551615;   // OK  
}  
```

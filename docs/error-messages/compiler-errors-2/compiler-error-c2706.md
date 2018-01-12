---
title: Compiler-Fehler C2706 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2706
dev_langs: C++
helpviewer_keywords: C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04527b1e67a2e25547631186add8ab5c323d1e26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2706"></a>Compiler-Fehler C2706 generiert
Ungültige __except ohne übereinstimmende \__finally (fehlende '}' in \__finally Block?)  
  
 Der Compiler eine schließende geschweifte Klammer für keinen finden eine `__try` Block.  
  
 Im folgende Beispiel wird C2706 generiert:  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```
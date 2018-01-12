---
title: Compilerfehler C2147 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2147
dev_langs: C++
helpviewer_keywords: C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef0499d7f012ad11217dc3d3cfda1347a5926a49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2147"></a>Compilerfehler C2147
Syntaxfehler: 'Bezeichner' ist ein neues Schlüsselwort  
  
 Ein Bezeichner wurde verwendet, die nun ein reserviertes Schlüsselwort in der Sprache.  
  
 Im folgende Beispiel wird C2147 generiert:  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```
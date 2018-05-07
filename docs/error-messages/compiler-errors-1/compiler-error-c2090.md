---
title: Compiler-Fehler C2090 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2090
dev_langs:
- C++
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718ed5ba8d422c2657dc58591ce285b0d85857cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2090"></a>Compiler-Fehler C2090 generiert
Funktion gibt ein array  
  
 Eine Funktion kann nicht auf ein Array zurückgeben. Geben Sie stattdessen einen Zeiger auf ein Array zurück.  
  
 Im folgende Beispiel wird C2090 generiert:  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 Mögliche Lösung:  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```
---
title: Compiler-Fehler C2090 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2090
dev_langs: C++
helpviewer_keywords: C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9a60a4e2d1a5db0a698e210ca5ed1360a96ffdc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
---
title: Compilerfehler Fehler C2665 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5a349df2c60d746b6b090953362c7c6801e1f2a3
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2665"></a>Compilerfehler Fehler C2665
'Funktion': kann keine Überladungen "number1" Parameter "number2" vom Typ "Typ" konvertieren  
  
 Ein Parameter der überladenen Funktionen kann nicht dem erforderlichen Typ konvertiert werden.  Folgende Lösungen möglich:  
  
-   Geben Sie einen Konvertierungsoperator.  
  
-   Verwenden Sie die explizite Konvertierung.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2665 generiert.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```

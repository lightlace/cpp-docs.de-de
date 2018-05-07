---
title: Compilerfehler Fehler C2665 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18cc99d6ea0a45e7c096a13cfe57dc841ca351bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
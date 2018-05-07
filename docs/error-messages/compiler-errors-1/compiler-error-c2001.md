---
title: Compilerfehler Fehler C2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f56eabbcb5ca322d7549c21a56893a8e13d9261
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2001"></a>Compilerfehler Fehler C2001
Zeilenvorschub in Konstante.  
  
 Eine Zeichenfolgenkonstante kann nicht auf eine zweite Zeile fortgesetzt werden, es sei denn, Sie die folgenden Schritte aus:  
  
-   Beenden Sie die erste Zeile mit einem umgekehrten Schrägstrich.  
  
-   Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie die Zeichenfolge in der nächsten Zeile in einer anderen doppeltes Anführungszeichen.  
  
 Beenden die erste Zeile mit \n ist nicht ausreichend.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2001 generiert:  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## <a name="example"></a>Beispiel  
 Leerzeichen am Anfang der nächsten Zeile nach einem Zeilenfortsetzungszeichen sind in die Zeichenfolgenkonstante enthalten. Keiner der oben genannten Beispiele sollten ein neue Zeilenumbruchzeichen in die Zeichenfolgenkonstante einbetten. Sie können ein Zeilenumbruchzeichen einbetten, wie hier gezeigt:  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```
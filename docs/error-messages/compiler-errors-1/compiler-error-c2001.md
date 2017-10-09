---
title: Compilerfehler Fehler C2001 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aedba438451089aa2d71e06da7ce189ab97d4190
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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

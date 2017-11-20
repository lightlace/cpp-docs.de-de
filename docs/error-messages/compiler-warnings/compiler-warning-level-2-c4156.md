---
title: Compilerwarnung (Stufe 2) C4156 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4156
dev_langs: C++
helpviewer_keywords: C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e60e8918d33594df6d362eeed3a195484962d32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4156"></a>Compilerwarnung (Stufe 2) C4156
Löschen eines Arrayausdrucks ohne Verwendung der Arrayform von "Delete". Arrayform ersetzt  
  
 Der nicht-Arrayform von **löschen** ein Array kann nicht gelöscht werden. Der Compiler übersetzte **löschen** in das Formular Array.  
  
 Diese Warnung tritt nur unter Microsoft-Erweiterungen (/ Ze).  
  
## <a name="example"></a>Beispiel  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```
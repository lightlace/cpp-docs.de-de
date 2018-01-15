---
title: Compilerwarnung (Stufe 4) C4295 | Microsoft Docs
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2018
---
# <a name="compiler-warning-level-4-c4295"></a>Compilerwarnung (Stufe 4) C4295
  
> "*Array*': Array ist zu klein, um ein abschließendes Nullzeichen enthalten.  
  
Ein Array wurde initialisiert, aber das letzte Zeichen im Array ist nicht Null; Zugreifen auf das Array als Zeichenfolge kann zu unerwarteten Ergebnissen führen.  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Beispiel wird C4295 generiert. Um dieses Problem zu beheben, konnten Sie deklarieren die Arraygröße größer, zum Speichern ein abschließendes Nullzeichen aus der Zeichenfolge Initialisierer, oder Sie können eine Initialisiererliste Array verwenden, um die beabsichtigte löschen, die sich dies ein Array von `char`, keine Null-terminierte Zeichenfolge.  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```

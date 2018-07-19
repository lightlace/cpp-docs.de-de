---
title: Compilerwarnung (Stufe 4) C4295 | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 815a669bc359121b13b1d636009cad81dc332304
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296301"
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

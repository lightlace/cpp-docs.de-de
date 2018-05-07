---
title: Compilerwarnung (Stufen 1 und 4) C4112 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43718511af0d85f0c9026fe70b4749c4e3d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Compilerwarnung (Stufen 1 und 4) C4112
\#Zeile muss eine ganze Zahl zwischen 1 und Zahl  
  
 Die [#line](../../preprocessor/hash-line-directive-c-cpp.md) -Direktive gibt einen ganzzahligen Parameter an, der außerhalb des zulässigen Bereichs liegt.  
  
 Wenn der angegebene Parameter kleiner als 1 ist, wird der Zeilenzähler auf 1 zurückgesetzt. Wenn der angegebene Parameter größer als *Anzahl*ist, der vom Compiler definierte Grenzwert, bleibt der Zeilenzähler unverändert. Dies ist eine Warnung der Stufe 1 unter ANSI-Kompatibilität ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung der Stufe 4 gemäß Microsoft-Extensions ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Im folgenden Beispiel wird C4112 generiert:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```
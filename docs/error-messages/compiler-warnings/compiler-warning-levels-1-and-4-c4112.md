---
title: Compilerwarnung (Stufen 1 und 4) C4112 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8a2c08b6c4bc8e1f2cf20e0236f76b5cd3020de4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Compilerwarnung (Stufen 1 und 4) C4112
\#Zeile muss eine ganze Zahl zwischen 1 und Zahl  
  
 Die [#line](../../preprocessor/hash-line-directive-c-cpp.md) -Direktive gibt einen ganzzahligen Parameter an, die außerhalb des zulässigen Bereichs liegt.  
  
 Wenn der angegebene Parameter kleiner als 1 ist, wird der Zeilenzähler auf 1 zurückgesetzt. Wenn der angegebene Parameter größer als *Anzahl*ist, der vom Compiler definierte Grenzwert, bleibt der Zeilenzähler unverändert. Dies ist eine Warnung der Stufe 1 unter ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)) und eine Warnung der Stufe 4 gemäß Microsoft-Erweiterungen (["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Im folgenden Beispiel wird C4112 generiert:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```

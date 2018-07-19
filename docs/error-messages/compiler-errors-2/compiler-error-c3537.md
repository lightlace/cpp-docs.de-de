---
title: Compilerfehler C3537 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3537
dev_langs:
- C++
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f03f02062e61e4034f0a809784ba571ce532e07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252604"
---
# <a name="compiler-error-c3537"></a>Compilerfehler C3537
'Typ': Sie können nicht eine Umwandlung in einen Typ, der "auto" enthält  
  
 Eine Variable auf den angegebenen Typ kann nicht umgewandelt werden, da der Typ enthält die `auto` -Schlüsselwort und die standardmäßige [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) (Compileroption) gültig ist.  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird C3537 erzeugt, da die Variablen in einen Typ umgewandelt werden, die enthält die `auto` Schlüsselwort.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../../cpp/auto-keyword.md)
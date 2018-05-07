---
title: Compilerwarnung (Stufe 1) C4190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e62f6bcfaa499338d5fde1d09cb91574241ce8a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4190"></a>Compilerwarnung (Stufe 1) C4190
"Bezeichner1" C-Bindung angegeben wurde, gibt aber UDT "Bezeichner2" die mit C nicht kompatibel ist  
  
 Eine Funktion oder ein Zeiger auf eine Funktion verfügt über einen UDT (benutzerdefinierte Typ, der eine Klasse, Struktur, Enumeration oder Union ist) als Rückgabetyp und `extern` "C"-Bindung. Dies ist zulässig wenn:  
  
-   Alle Aufrufe dieser Funktion auftreten von C++.  
  
-   Die Definition der Funktion ist in C++.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```
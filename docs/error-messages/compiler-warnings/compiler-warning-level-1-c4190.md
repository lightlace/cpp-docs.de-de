---
title: Compilerwarnung (Stufe 1) C4190 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 127eb4327826412d605f2a4a008e411880998073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
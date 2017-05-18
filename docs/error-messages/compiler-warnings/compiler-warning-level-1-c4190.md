---
title: Compiler (Stufe 1) C4190 | Microsoft-Dokumentation
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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf45c0737f52da93f93c1f95d313771f0e92a10e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4190"></a>Compiler (Stufe 1) C4190
'Bezeichner1' hat C-Bindung angegeben, gibt aber UDT 'Bezeichner2' was mit C inkompatibel ist  
  
 Eine Funktion oder ein Zeiger auf eine Funktion verfügt über einen UDT (benutzerdefinierten Typ, der eine Klasse, Struktur, Enum oder Union ist) als Rückgabetyp und `extern` C-Bindung. Dies ist zulässig wenn:  
  
-   Alle Aufrufe dieser Funktion erfolgen von C++ aus.  
  
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

---
title: Compiler-Fehler C3609 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3609
dev_langs:
- C++
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: 11
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ffb46df64ac0a18847c3595f9fb3fffc3bd26c51
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3609"></a>Compilerfehler C3609
„Member“: Eine versiegelte oder endgültige Funktion muss virtuell sein.  
  
 Die [versiegelte](../../windows/sealed-cpp-component-extensions.md) und [letzten](../../cpp/final-specifier.md) Schlüsselwörter dürfen nur auf eine Klasse, Struktur oder Memberfunktion Funktion `virtual`.  
  
 Im folgenden Beispiel wird C3609 generiert:  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  


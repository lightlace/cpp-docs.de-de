---
title: Compilerfehler Fehler C3156 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3156
dev_langs:
- C++
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 793b143fa42e790610a086782c4bf99369965e1f
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3156"></a>Compilerfehler Fehler C3156
'class': Sie können nicht über eine lokale Definition eines verwalteten oder WinRT-Typs verfügen  
  
 Eine Funktion kann weder die Definition noch die Deklaration einer verwalteten oder WinRT-Klasse, -Struktur oder -Oberfläche enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3156 generiert:  
  
```  
// C3156.cpp  
// compile with: /clr /c  
void f() {  
   ref class X {};   // C3156  
   ref class Y;   // C3156  
}  
```  


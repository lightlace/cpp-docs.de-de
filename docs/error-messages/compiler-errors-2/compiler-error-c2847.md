---
title: Compilerfehler C2847 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
caps.latest.revision: 12
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
ms.openlocfilehash: 004b3b4474593ac4350e35fd48309a271948a3ea
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2847"></a>Compilerfehler C2847
sizeof kann nicht auf verwalteten oder WinRT-Typ „Klasse“ angewendet werden.  
  
 Die [Sizeof](../../cpp/sizeof-operator.md) -Operator erhält den Wert eines Objekts zur Kompilierungszeit. Die Größe einer verwalteten oder WinRT-Klasse, Schnittstelle oder eines Werttyps ist dynamisch und ist zur Kompilierzeit nicht bekannt.  
  
 Im folgenden Beispiel wird C2847 generiert:  
  
```  
// C2847.cpp  
// compile with: /clr  
ref class A {};  
  
int main() {  
   A ^ xA = gcnew A;  
   sizeof(*xA);   // C2847 cannot use sizeof on managed object  
}  
```  


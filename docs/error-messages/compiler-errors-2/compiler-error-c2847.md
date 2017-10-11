---
title: Compilerfehler C2847 | Microsoft Docs
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8406ea786def9c3241a0ae1de8743d53e91f96cd
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2847"></a>Compilerfehler C2847
sizeof kann nicht auf verwalteten oder WinRT-Typ „Klasse“ angewendet werden.  
  
 Die ["sizeof"](../../cpp/sizeof-operator.md) Operator Ruft den Wert eines Objekts zum Zeitpunkt der Kompilierung. Die Größe einer verwalteten oder WinRT-Klasse, Schnittstelle oder eines Werttyps ist dynamisch und ist zur Kompilierzeit nicht bekannt.  
  
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


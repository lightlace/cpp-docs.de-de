---
title: Compilerfehler C2847 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2847
dev_langs:
- C++
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd18d685649c5ad8f03e3fdbb8b375717227f4c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

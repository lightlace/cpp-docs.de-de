---
title: Compilerfehler C2273 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f49ee00ba5617b494e27650c38dad679ae6767a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170868"
---
# <a name="compiler-error-c2273"></a>Compilerfehler C2273
'Typ': unzulässig auf der rechten Seite des Operators "->"  
  
 Ein Typ wird als der Rechte Operand des eine `->` Operator.  
  
 Dieser Fehler kann verursacht werden, indem Sie versuchen, eine Konvertierung für einen benutzerdefinierten Typ zugreifen. Verwenden Sie das Schlüsselwort `operator` zwischen -> und `type`.  
  
 Im folgende Beispiel wird C2273 generiert:  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```
---
title: Compilerwarnung (Stufe 1) C4369 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4369
dev_langs:
- C++
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63445f0713b43ce7fde418ebd9d65403965c07ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4369"></a>Compilerwarnung (Stufe 1) C4369
'Enumerator': der Enumeratorwert "Value" kann nicht als 'Type' dargestellt werden, Wert ist 'New_value'  
  
 Ein Enumerator wurde größer sein als der größte Wert für den angegebenen zugrunde liegenden Typ berechnet.  Dies verursacht einen Überlauf und der Compiler umschlossen den Enumeratorwert, der niedrigst mögliche Wert für den Typ.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4369 generiert.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```
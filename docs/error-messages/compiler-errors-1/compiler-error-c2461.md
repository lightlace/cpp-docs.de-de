---
title: Compilerfehler C2461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47aee3122dad3e875cf58d5a41bcadda297e1463
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197636"
---
# <a name="compiler-error-c2461"></a>Compilerfehler C2461
  
> "*Klasse*': Konstruktor fehlt formalen Parameter  
  
 Der Konstruktor für die Klasse ist keine formalen Parameter angeben. Die Deklaration eines Konstruktors muss es sich um eine Liste formaler Parameter angeben. Die Liste kann leer sein.  
  
Um dieses Problem zu beheben, fügen Sie ein Klammernpaar nach der Deklaration von *Klasse*:: **Klasse*.  
  
## <a name="example"></a>Beispiel  
  
Im folgende Beispiel wird gezeigt, wie C2461 generiert diesen Fehler beheben:  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```
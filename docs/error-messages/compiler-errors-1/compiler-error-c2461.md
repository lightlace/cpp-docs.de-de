---
title: Compilerfehler C2461 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5e1593e37bd3a02897d023e308593e23d3d73b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
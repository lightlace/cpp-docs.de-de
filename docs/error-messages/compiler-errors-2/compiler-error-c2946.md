---
title: Compilerfehler C2946 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 887afb5a42a7dac47b5d3b8490acf8256601f189
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2946"></a>Compilerfehler C2946
Explizite Instanziierung: "Klasse" ist keine Spezialisierung einer Vorlagenklasse  
  
 Nicht auf Vorlagen basierende Klassen können nicht explizit instanziiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2946 generiert.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```
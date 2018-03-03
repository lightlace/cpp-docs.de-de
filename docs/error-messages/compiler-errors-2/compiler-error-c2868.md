---
title: Compilerfehler C2868 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7255aa3e73e23109535ae0e83d6e9bd907cdbcd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2868"></a>Compilerfehler C2868  
  
> "*Bezeichner*': Ungültige Syntax für using-Deklaration; vollständiger Name erwartet  
  
Ein [using-Deklaration](../../cpp/using-declaration.md) erfordert eine *qualifizierten Namen*, einen Bereichsoperator (`::`) getrennte Sequenz mit Namespace, Klasse oder eines Enumerationswerts Namen, die mit den Namen des Bezeichners endet. Ein einzelnes Bereichsauflösungsoperator kann verwendet werden, um einen Namen aus dem globalen Namespace einzuführen.  
  
## <a name="example"></a>Beispiel  
  
Im folgenden Beispiel wird C2868 generiert und zeigt außerdem die richtige Verwendung:  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```
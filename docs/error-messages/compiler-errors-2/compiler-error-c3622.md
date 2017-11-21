---
title: Compilerfehler C3622 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3622
dev_langs: C++
helpviewer_keywords: C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a5ebccc9fb6cc8c25a8a6b42ae3b99439b1f5d44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3622"></a>Compilerfehler C3622
'Klasse': eine Klasse deklariert, wie 'Schlüsselwort' kann nicht instanziiert werden  
  
Es wurde versucht, beim Instanziieren einer Klasse, die als gekennzeichnete [abstrakte](../../windows/abstract-cpp-component-extensions.md). Eine Klasse als markiert `abstract` können eine Basisklasse sein, aber nicht instanziiert werden.  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C3622 generiert.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  

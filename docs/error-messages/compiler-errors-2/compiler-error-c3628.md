---
title: Compilerfehler C3628 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16e2e2a83cc5dbf52e7030e10d00c3cdfe7891d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3628"></a>Compilerfehler C3628
'base Class': verwaltete oder WinRTclasses unterstützen nur öffentliche Vererbung  
  
Es wurde versucht, mithilfe eines verwalteten oder WinRT Klasse als eine [private](../../cpp/private-cpp.md) oder [geschützt](../../cpp/protected-cpp.md) Basisklasse. Eine verwaltete oder WinRT-Klasse kann nur verwendet werden, als eine Basisklasse mit [öffentlichen](../../cpp/public-cpp.md) Zugriff.  
  
Im folgenden Beispiel wird C3628 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  

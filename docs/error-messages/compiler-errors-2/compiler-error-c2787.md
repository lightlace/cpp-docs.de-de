---
title: Compiler-Fehler C2787 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 71924ae6e24eba04e27ec366ef73dedc2fa65263
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2787"></a>Compiler-Fehler C2787 generiert
'Bezeichner': keine GUID dieses Objekt zugeordnet wurde  
  
 Die [__uuidof](../../cpp/uuidof-operator.md) -Operator hat einen benutzerdefinierten Typ mit einer GUID verbundenen oder ein Objekt eines solchen benutzerdefinierten Typs. Dieser Fehler tritt auf, wenn das Argument einen benutzerdefinierten Typ ohne GUID ist.  
  
 Im folgende Beispiel wird C2787 generiert:  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```

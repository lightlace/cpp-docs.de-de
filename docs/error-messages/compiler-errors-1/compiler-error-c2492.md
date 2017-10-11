---
title: Compilerfehler C2492 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68268be94897e3c648e95185877dec9e276355c4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2492"></a>Compilerfehler C2492
"*Variable*": Daten mit Speicherdauer Thread können keine Dll-Schnittstelle    
  
 Die Variable wird deklariert, mit der [Thread](../../cpp/thread.md) -Attribut und mit der DLL-Schnittstelle. Die Adresse der `thread` Variable ist nicht erst zur Laufzeit bekannt, damit es mit einer DLL-Import oder Export verknüpft werden kann.  
  
 Im folgende Beispiel wird C2492 generiert:  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```

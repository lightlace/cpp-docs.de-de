---
title: Compilerfehler C3062 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1eebf751c267e9688eebb8c679fe801f77cfa4c0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3062"></a>Compilerfehler C3062
"Enum": Enumerator ist ein Wert erforderlich, da der zugrunde liegende Typ 'Typ' ist  
  
 Sie können einen zugrunde liegender Typ für eine Enumeration angeben. Einige Datentypen erfordern jedoch das Zuweisen von Werten für jeden Enumerator.  
  
 Weitere Informationen über Enumerationen finden Sie unter [Enumerationsklasse](../../windows/enum-class-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3062 generiert:  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```

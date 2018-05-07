---
title: Compilerfehler C3062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da507511cb5f091d5d9432bbfeb36951e3f43c6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
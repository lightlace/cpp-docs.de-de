---
title: Compilerfehler C3384 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3384
dev_langs:
- C++
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ce70a37639288bce3244f48635ae4b756bb98cad
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3384"></a>Compilerfehler C3384
"type_parameter" : Die Werteinschränkung und die ref-Einschränkung schließen sich gegenseitig aus  
  
 Sie können einen generischen Typ nicht gleichzeitig auf `value class` und `ref class`einschränken.  
  
 Finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3384 generiert.  
  
```  
// C3384.cpp  
// compile with: /c /clr  
generic <typename T>  
where T : ref class  
where T : value class   // C3384  
ref class List {};  
```

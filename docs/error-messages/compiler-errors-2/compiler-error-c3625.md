---
title: Compilerfehler C3625 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3625
dev_langs:
- C++
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c49600c823965dc92e0decab3048f076169d43fe
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3625"></a>Compilerfehler C3625
„native_type“: Ein systemeigener Typ kann nicht vom verwalteten oder WinRT-Typ „Typ“ abgeleitet werden.  
  
Eine systemeigene Klasse kann nicht von einer verwalteten oder WinRT-Klasse erben. Weitere Informationen finden Sie unter [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3625 generiert:  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  


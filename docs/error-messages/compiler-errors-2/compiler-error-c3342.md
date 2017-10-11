---
title: Compilerfehler C3342 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3342
dev_langs:
- C++
helpviewer_keywords:
- C3342
ms.assetid: 5c6d784f-bebe-4f7e-8615-44ca6f78bfba
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4dc1432c6cf89f339094535f5b4ccbbd9af90aa9
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3342"></a>Compilerfehler C3342
'attribut': Mehrdeutiges Attribut  
  
 Der Compiler hat mehr als eine Definition eines Attributs gefunden.  
  
 Ein Attribut wurde mehrmals definiert.  
  
 Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3342 generiert:  
  
```  
// C3342.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Reflection;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref class XAttribute : public  Attribute {};  
  
[AttributeUsage(AttributeTargets::All)]  
public ref class X : public Attribute {};  
  
[X]   // C3342 could refer to X or XAttribute  
// try the following line instead  
// [XAttribute]  
public ref class Class4 {};  
```

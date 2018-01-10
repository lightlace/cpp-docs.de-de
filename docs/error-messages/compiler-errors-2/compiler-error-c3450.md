---
title: Compilerfehler C3450 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3450
dev_langs: C++
helpviewer_keywords: C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 970631a125f07e61a0923703678642e357426dc5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3450"></a>Compilerfehler C3450
„Typ“: ist kein Attribut. [System::AttributeUsageAttribute] oder [Windows::Foundation::Metadata::AttributeUsageAttribute] darf nicht angegeben werden.  
  
 Ein benutzerdefiniertes verwaltetes Attribut muss von <xref:System.ComponentModel.AttributeCollection.%23ctor%2A> erben. Ein Windows-Runtime-Attribut muss im `Windows::Foundation::Metadata`-Namespace definiert sein.  
  
 Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3450 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C3450.cpp  
// compile with: /clr  
// C3450 expected  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref struct AtClass {  
   AtClass(Type ^) {}  
};  
  
[attribute(AttributeTargets::All)]  
ref struct AtClass2 {  
   AtClass2() {}  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
// Delete the following line to resolve.  
ref class B {};  
// Uncomment the following line to resolve.  
// ref class B : Attribute {};  
```
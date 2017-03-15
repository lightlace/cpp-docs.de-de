---
title: "Compiler Error C3450 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3450"
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compiler Error C3450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Typ“: ist kein Attribut. \[System::AttributeUsageAttribute\] oder \[Windows::Foundation::Metadata::AttributeUsageAttribute\] darf nicht angegeben werden.  
  
 Ein benutzerdefiniertes verwaltetes Attribut muss von <xref:System.ComponentModel.AttributeCollection.#ctor*> erben.  Ein Windows\-Runtime\-Attribut muss im `Windows::Foundation::Metadata`\-Namespace definiert sein.  
  
 Weitere Informationen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Beispiel  
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
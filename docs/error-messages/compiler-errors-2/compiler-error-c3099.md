---
title: "Compiler Error C3099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3099"
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compiler Error C3099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort': Verwendung des \[System::AttributeUsageAttribute\] für verwaltete Attribute; Verwendung des \[Windows::Foundation::Metadata::AttributeUsageAttribute\] für WinRT\-Attribute  
  
 Verwendung von <xref:System.AttributeUsageAttribute> zum Deklarieren von **\/clr**Attributen.  Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows\-Runtime\-Attributen.  
  
 Weitere Informationen zu CLR\-Attributen finden Sie unter [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  Unterstützte Attribute in Windows\-Runtime finden Sie unter [Windows.Foundation.Metadata\-Namespace](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## Beispiel  
 Im folgenden Beispiel wird C3099 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```
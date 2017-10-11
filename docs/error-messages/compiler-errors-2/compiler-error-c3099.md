---
title: Compilerfehler C3099 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b0303ef909d6f18cb54c70bc64ab06d415e96da5
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3099"></a>Compilerfehler C3099
'Schlüsselwort': Verwendung des [System::AttributeUsageAttribute] für verwaltete Attribute; Verwendung des [Windows::Foundation::Metadata::AttributeUsageAttribute] für WinRT-Attribute  
  
 Verwendung <xref:System.AttributeUsageAttribute> deklarieren **"/ CLR"** Attribute. Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows-Runtime-Attributen.  
  
 Weitere Informationen zu CLR-Attributen finden Sie unter [benutzerdefinierte Attribute](../../windows/user-defined-attributes-cpp-component-extensions.md). Unterstützte Attribute in Windows-Runtime finden Sie unter [Windows.Foundation.Metadata-Namespace](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## <a name="example"></a>Beispiel  
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

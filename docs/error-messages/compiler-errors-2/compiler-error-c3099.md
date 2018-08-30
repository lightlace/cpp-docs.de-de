---
title: Compilerfehler C3099 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3099
dev_langs:
- C++
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea57a79fab92152824b7c9aaf0c5d50c14fee32e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211994"
---
# <a name="compiler-error-c3099"></a>Compilerfehler C3099
'Schlüsselwort': Verwendung des [System::AttributeUsageAttribute] für verwaltete Attribute; Verwendung des [Windows::Foundation::Metadata::AttributeUsageAttribute] für WinRT-Attribute  
  
 Verwendung <xref:System.AttributeUsageAttribute> deklarieren **"/ CLR"** Attribute. Verwendung von `Windows::Foundation::Metadata::AttributeUsageAttribute` zum Deklarieren von Windows-Runtime-Attributen.  
  
 Weitere Informationen zu CLR-Attributen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Unterstützte Attribute in Windows-Runtime, finden Sie unter [Windows.Foundation.Metadata-Namespace](https://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
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
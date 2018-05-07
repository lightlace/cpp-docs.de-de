---
title: Compilerfehler C3451 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3451
dev_langs:
- C++
helpviewer_keywords:
- C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a8aa09f0eb38364179be1608c3f230fe8059509
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3451"></a>Compilerfehler C3451
'Attribut': nicht verwaltetes Attribut "Typ" kann nicht angewendet werden.  
  
 Eine C++-Attribut kann nicht in einen CLR-Typ angewendet werden. Finden Sie unter [C++-Attributreferenz](../../windows/cpp-attributes-reference.md) für Weitere Informationen.  
  
 Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Dieser Fehler kann infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: die [Uuid](../../windows/uuid-cpp-attributes.md) Attribut ist für ein benutzerdefiniertes Attribut mithilfe von CLR-Programmierung nicht mehr zulässig. Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.GuidAttribute>.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3451 generiert.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```
---
title: Compilerfehler C3813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e947b281c90c4d2ace83971f1de972c29bde72ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3813"></a>Compilerfehler C3813
eine Eigenschaftendeklaration kann nur in der Definition eines verwalteten oder WinRT-Typs auftreten.  
  
Ein [Eigenschaft](../../dotnet/how-to-use-properties-in-cpp-cli.md) kann nur innerhalb eines verwalteten oder Windows-Runtime deklariert sein Typ. Systemeigene Typen unterstützen das `property`-Schlüsselwort nicht.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3813 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```
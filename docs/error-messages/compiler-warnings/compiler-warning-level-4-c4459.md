---
title: Compilerwarnung (Stufe 4) C4459 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93bdbfe6cceff664e7b7a5f8cee20e8df51e2fb4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294507"
---
# <a name="compiler-warning-level-4-c4459"></a>Compilerwarnung (Stufe 4) C4459
  
> Deklaration von "*Bezeichner*" Blendet globale Deklaration
  
Die Deklaration von *Bezeichner* im lokalen Gültigkeitsbereich Blendet Sie aus der Deklaration der identisch benannt *Bezeichner* im globalen Bereich. Diese Warnung teilt Ihnen, die Verweise auf *Bezeichner* in diesem Bereich auf die lokal deklarierte-Version nicht die globale Version, die nicht unbedingt Ihren Zweck zu beheben. Im Allgemeinen wird empfohlen, dass Sie die globalen Variablen als ein gutes Entwicklungsverfahren minimieren. Um Verunreinigung des globalen Namespace zu minimieren, empfehlen wir die Verwendung eines benannten Namespaces für globale Variablen.  
  
Diese Warnung ist neu in Visual Studio 2015 in Visual C++ Compilerversion 18.00 Uhr. Um Warnungen zu dieser Version des Compilers oder später während der Migration von Code zu unterdrücken, verwenden Sie die [/Wv:18](../../build/reference/compiler-option-warning-level.md) -Compileroption. 

## <a name="example"></a>Beispiel
  
 Im folgenden Beispiel wird C4459 generiert:  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
Eine Möglichkeit, dieses Problem zu beheben ist, erstellen einen Namespace für Ihre Globals, jedoch nicht verwenden eine `using` Richtlinie auf diesen Namespace in den Bereich, bringen, damit alle Verweise, die eindeutig verwenden müssen qualifizierten Namen:  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  

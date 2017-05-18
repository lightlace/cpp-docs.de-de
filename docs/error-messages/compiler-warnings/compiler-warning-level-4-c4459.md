---
title: Compilerwarnung (Stufe 4) C4459 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 87550474065639f6e1c7521ebfe76792d748ce9b
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

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


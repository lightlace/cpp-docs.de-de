---
title: Compiler-Warnung (Stufe 1) C4917 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 43dce460fb336b09ce39d3e4c0e52b43a175ea36
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4917"></a>Compilerwarnung (Stufe 1) C4917
'Deklarator': eine GUID kann nur eine Klasse, Schnittstelle oder Namespace zugeordnet werden  
  
Eine benutzerdefinierte Struktur als [Klasse](../../cpp/class-cpp.md), [Schnittstelle](../../cpp/interface.md), oder [Namespace](../../cpp/namespaces-cpp.md) kann nicht über eine GUID verfügen.  
  
Diese Warnung ist standardmäßig deaktiviert. Finden Sie unter [Compiler Warnungen, die Are Off standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md) Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
Im folgenden Codebeispiel wird C4917 generiert:  
  
```cpp  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```

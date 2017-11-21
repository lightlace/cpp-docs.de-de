---
title: Compilerwarnung (Stufe 1) C4917 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4917
dev_langs: C++
helpviewer_keywords: C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3b5d930b0c8a79542526adcd174a9ed6a0a8db4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4917"></a>Compilerwarnung (Stufe 1) C4917
'Deklarator': eine GUID kann nur eine Klasse, Schnittstelle oder ein Namespace zugeordnet werden  
  
Eine benutzerdefinierte Struktur außer [Klasse](../../cpp/class-cpp.md), [Schnittstelle](../../cpp/interface.md), oder [Namespace](../../cpp/namespaces-cpp.md) keine GUID.  
  
Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
## <a name="example"></a>Beispiel  
Im folgenden Codebeispiel wird die C4917 generiert:  
  
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
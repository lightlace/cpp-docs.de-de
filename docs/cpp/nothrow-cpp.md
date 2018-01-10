---
title: Nothrow (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: nothrow_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a6200a8207fdf25b533c7db7e05247797592744e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nothrow-c"></a>nothrow (C++)
**Microsoft-spezifisch**  
  
 Ein erweitertes `__declspec`-Attribut, das in der Deklaration von Funktionen verwendet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Attribut weist den Compiler an, dass die deklarierte Funktion und die Funktionen, die aufgerufen werden, nie eine Ausnahme auslösen. Mit dem Modell für synchrone Ausnahmebehandlung kann der Compiler nun standardmäßig die Mechanismen der Lebensdauerverfolgung gewisser entladbarer Objekte in einer solchen Funktion eliminieren, wodurch die Codegröße erheblich reduziert wird. Bei der Präprozessoranweisung sind die folgenden drei Funktionsdeklarationen gleichwertig:  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 Die Verwendung von `void __declspec(nothrow) __stdcall f2();` hat den Vorteil, dass Sie eine API-Definition verwenden können, wie die von der `#define`-Anweisung veranschaulichte Definition, um `nothrow` auf einem Satz von Funktionen anzugeben. Die dritte Deklaration`, void __stdcall f3() throw();` ist die Syntax, die vom C++-Standard definiert wird.  
  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)
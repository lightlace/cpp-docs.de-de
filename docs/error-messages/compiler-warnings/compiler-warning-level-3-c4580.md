---
title: Compiler (Stufe 3) C4580 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
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
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: c8cebbda1d3472a2efda43f816e7a13f2f460408
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4580"></a>Compilerwarnung (Stufe 3) C4580
[attribute] ist veraltet; geben Sie stattdessen System::Attribute oder Platform::Metadata als Basisklasse an.  
  
[[Attribut](../../windows/attribute.md)] ist nicht mehr die bevorzugte Syntax zum Erstellen von benutzerdefinierten Attributen. Weitere Informationen finden Sie unter [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Leiten Sie für CLR-Code Attribute aus `System::Attribute` ab. Leiten Sie für Windows-Runtime-Code Attribute aus `Platform::Metadata` ab.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3454 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```cpp  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```

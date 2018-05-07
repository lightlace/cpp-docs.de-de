---
title: Compilerfehler C3454 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65e1aea19dbeab5c34a6b818afcb4cd4a7deda91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3454"></a>Compilerfehler C3454
[attribut] ist in der Klassendeklaration nicht zulässig  
  
 Es muss eine Klasse für es definiert werden, damit es ein Attribut sein kann.  
  
 Weitere Informationen finden Sie unter [attribute](../../windows/attribute.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3454 generiert:  
  
```  
// C3454.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute]   // C3454  
ref class Attr1;  
  
[attribute]   // OK  
ref class Attr2 {};  
```
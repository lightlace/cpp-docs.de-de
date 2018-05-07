---
title: Compilerfehler C3888 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c11c897f35a6c395c4bc6ee6a64be51fa810911b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3888"></a>Compilerfehler C3888
"name": Der diesem literal-Datenmember zugeordnete Konstantenausdruck wird von C++/CLI nicht unterstützt  
  
 Das *name* -Datenmember, das mit dem [literal](../../windows/literal-cpp-component-extensions.md) -Schlüsselwort deklariert wird, wird mit einem Wert initialisiert, der vom Compiler nicht unterstützt wird. Der Compiler unterstützt nur konstante integrale, Enumerations- oder Zeichenfolgentypen. Der Fehler **C3888** wurde wahrscheinlich dadurch verursacht, dass das Datenmember mit einem Bytearray initialisiert wird.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass das deklarierte literal-Datenmember ein unterstützter Typ ist.  
  
## <a name="see-also"></a>Siehe auch  
 [literal](../../windows/literal-cpp-component-extensions.md)
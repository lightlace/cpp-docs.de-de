---
title: Compilerfehler C3888 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 26e55c8a675ada3fd2e88976bc9d9a51cfa8b751
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3888"></a>Compilerfehler C3888
"name": Der diesem literal-Datenmember zugeordnete Konstantenausdruck wird von C++/CLI nicht unterstützt  
  
 Das *name* -Datenmember, das mit dem [literal](../../windows/literal-cpp-component-extensions.md) -Schlüsselwort deklariert wird, wird mit einem Wert initialisiert, der vom Compiler nicht unterstützt wird. Der Compiler unterstützt nur konstante integrale, Enumerations- oder Zeichenfolgentypen. Der Fehler **C3888** wurde wahrscheinlich dadurch verursacht, dass das Datenmember mit einem Bytearray initialisiert wird.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Vergewissern Sie sich, dass das deklarierte literal-Datenmember ein unterstützter Typ ist.  
  
## <a name="see-also"></a>Siehe auch  
 [literal](../../windows/literal-cpp-component-extensions.md)
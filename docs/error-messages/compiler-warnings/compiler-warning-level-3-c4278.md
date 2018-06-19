---
title: Compilerwarnung (Stufe 3) C4278 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b556166f61c5d77ac34fb7243ac25d5baeaa2b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296675"
---
# <a name="compiler-warning-level-3-c4278"></a>Compilerwarnung (Stufe 3) C4278
'Bezeichner': Bezeichner in der Typbibliothek "Tlb" ist bereits ein Makro; Verwenden Sie den Qualifizierer "Umbenennen"  
  
 Bei Verwendung [#import](../../preprocessor/hash-import-directive-cpp.md), ein Bezeichner in der Typbibliothek, die Sie importieren versucht, einen Bezeichner deklarieren ***Bezeichner***. Dies ist jedoch bereits ein gültiges Symbol.  
  
 Verwenden der `#import` **umbenennen** Attribut, auf das Symbol in der Typbibliothek einen Alias zuzuweisen.
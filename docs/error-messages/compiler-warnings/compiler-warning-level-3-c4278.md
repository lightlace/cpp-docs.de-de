---
title: Compilerwarnung (Stufe 3) C4278 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4278
dev_langs: C++
helpviewer_keywords: C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 249b13b70f3f10942852d7a9aa13dcf4f08e1f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4278"></a>Compilerwarnung (Stufe 3) C4278
'Bezeichner': Bezeichner in der Typbibliothek "Tlb" ist bereits ein Makro; Verwenden Sie den Qualifizierer "Umbenennen"  
  
 Bei Verwendung [#import](../../preprocessor/hash-import-directive-cpp.md), ein Bezeichner in der Typbibliothek, die Sie importieren versucht, einen Bezeichner deklarieren ***Bezeichner***. Dies ist jedoch bereits ein gültiges Symbol.  
  
 Verwenden der `#import` **umbenennen** Attribut, auf das Symbol in der Typbibliothek einen Alias zuzuweisen.
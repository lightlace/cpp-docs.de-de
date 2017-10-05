---
title: Atexit mit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 4093bf14422fb6598f53d298aa8958a506103fb2
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="using-atexit"></a>Verwenden von "atexit"
Mit der [Atexit](../c-runtime-library/reference/atexit.md) -Funktion, geben Sie eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Es werden keine globalen statischen Objekte, die vor dem Aufruf von `atexit` initialisiert werden, vor Ausführung der Funktion zur Beendigung der Verarbeitung zerstört.  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)

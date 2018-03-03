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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7aec0e5aedb2d17e7d22b4f480eaef2be26413fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-atexit"></a>Verwenden von "atexit"
Mit der [Atexit](../c-runtime-library/reference/atexit.md) -Funktion, geben Sie eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Es werden keine globalen statischen Objekte, die vor dem Aufruf von `atexit` initialisiert werden, vor Ausführung der Funktion zur Beendigung der Verarbeitung zerstört.  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)
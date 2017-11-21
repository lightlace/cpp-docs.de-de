---
title: Atexit mit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords: atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 271dee456d47f9ef6286b4a9543583145f69bc41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="using-atexit"></a>Verwenden von "atexit"
Mit der [Atexit](../c-runtime-library/reference/atexit.md) -Funktion, geben Sie eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Es werden keine globalen statischen Objekte, die vor dem Aufruf von `atexit` initialisiert werden, vor Ausführung der Funktion zur Beendigung der Verarbeitung zerstört.  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)
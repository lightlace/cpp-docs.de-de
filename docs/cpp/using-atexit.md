---
title: Mithilfe von "atexit" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4acd81a5420f9fe2685e7570f26fea61691b845
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467403"
---
# <a name="using-atexit"></a>Verwenden von "atexit"
Mit der [von "atexit"](../c-runtime-library/reference/atexit.md) -Funktion, Sie können angeben, eine Beendigung der Verarbeitung-Funktion, die vor der Beendigung des Programms ausgeführt wird. Keine globalen statischen Objekts vor dem Aufruf von initialisiert **von "atexit"** werden vor der Ausführung der Funktion für die Beendigung der Verarbeitung zerstört.  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)
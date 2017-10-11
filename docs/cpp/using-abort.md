---
title: Mithilfe von Abort | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 690e76eb3b83844e0fed81bf8d7bbd4c395abb14
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="using-abort"></a>Verwenden von "abort"
Aufrufen der [abort](../c-runtime-library/reference/abort.md) -Funktion bewirkt eine sofortige Beendigung. Dies umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte. Außerdem wird jegliche spezielle Verarbeitung umgangen, die mit der `atexit`-Funktion angegeben wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)

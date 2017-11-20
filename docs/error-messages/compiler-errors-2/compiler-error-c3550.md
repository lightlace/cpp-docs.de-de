---
title: Compilerfehler C3550 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3550
dev_langs: C++
helpviewer_keywords: C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 52b3e3323bac9ad55ff10481b3504e4e054ba874
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3550"></a>Compilerfehler C3550
In diesem Kontext ist nur ein einfaches "decltype(auto)" zulässig.  
  
 Wenn `decltype(auto)` als Platzhalter für den Rückgabetyp einer Funktion dient, muss dieses allein verwendet werden. Es kann nicht als Teil der Zeigerdeklaration (`decltype(auto*)`), einer Verweisdeklaration (`decltype(auto&)`) oder einer anderen Qualifizierung dieser Art verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [auto](../../cpp/auto-cpp.md)
---
title: Veraltete Aufrufkonventionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs: C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 325a9a98ec536eaabedef3a93fbe38ccc2016cd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="obsolete-calling-conventions"></a>Veraltete Aufrufkonventionen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die **__pascal**, **__fortran**, und **__syscall** Aufrufkonventionen werden nicht mehr unterstützt. Sie können ihre Funktionalität emulieren, indem Sie eine der unterstützten Aufrufkonventionen und geeignete Linkeroptionen verwenden.  
  
 WINDOWS. H unterstützt jetzt auch die **WINAPI** -Makro, das in die entsprechende Aufrufkonvention für das Ziel übersetzt. Verwendung **WINAPI** , in dem zuvor verwendeten **PASCAL** oder **__far \__pascal**.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)
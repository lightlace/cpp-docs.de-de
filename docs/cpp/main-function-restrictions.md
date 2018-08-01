---
title: Einschränkungen der Main-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 981d4c8c0ef30993811e5dbb6fd0a112a6447011
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406493"
---
# <a name="main-function-restrictions"></a>Einschränkungen der main-Funktion
Mehrere Einschränkungen gelten für die **main** -Funktion, die nicht für andere C++-Funktionen gelten. Die **main** Funktion:  
  
-   Kann nicht überladen werden (siehe [Funktionsüberladung](function-overloading.md)).  
  
-   Kann nicht deklariert werden, als **Inline**.  
  
-   Kann nicht deklariert werden, als **statische**.  
  
-   Ihre Adresse kann nicht übernommen werden.  
  
-   Kann nicht aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)
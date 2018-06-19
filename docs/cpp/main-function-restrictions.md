---
title: Einschränkungen der Main-Funktion | Microsoft Docs
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
ms.openlocfilehash: ed5be2df6e152b26bcade1970b35ad33655e8e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419684"
---
# <a name="main-function-restrictions"></a>Einschränkungen der main-Funktion
Mehrere Einschränkungen gelten für die **main** -Funktion, die auf andere C++-Funktionen nicht anwendbar sind. Die **main** Funktion:  
  
-   Kann nicht überladen werden (siehe [Funktionsüberladung](function-overloading.md)).  
  
-   Kann nicht deklariert werden, als **Inline**.  
  
-   Kann nicht deklariert werden, als **statische**.  
  
-   Ihre Adresse kann nicht übernommen werden.  
  
-   Kann nicht aufgerufen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)
---
title: "Einschränkungen der Main-Funktion | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Main
dev_langs: C++
helpviewer_keywords: main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a94844a0d5636c58a764114ed6f413923d69950
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
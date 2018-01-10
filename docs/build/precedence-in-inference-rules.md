---
title: "Vorrang in Rückschlussregeln | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7374da0541fc66464947af5a7b2ea7ea7b5c1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-inference-rules"></a>Vorrang in Rückschlussregeln
Wenn eine Rückschlussregel mehrfach definiert ist, wird NMAKE die Definition die höchsten Rangfolge verwendet. Die folgende Liste zeigt die Reihenfolge der Priorität von der höchsten zur niedrigsten:  
  
1.  Eine Rückschlussregel in einem Makefile definiert. höhere Definitionen haben Vorrang vor.  
  
2.  Eine Rückschlussregel in Tools.ini definiert. höhere Definitionen haben Vorrang vor.  
  
3.  Eine vordefinierte Rückschlussregel.  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)
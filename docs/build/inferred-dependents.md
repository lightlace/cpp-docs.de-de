---
title: "Hergeleitete abhängige Elemente | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 410e52dd9ee9605f6e29b81491bda0f4883e1cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien
Eine hergeleitete abhängige eine Rückschlussregel abgeleitet wird und vor expliziten abhängigen Dateien ausgewertet wird. Wenn eine hergeleitete abhängige in Bezug auf ihr Ziel veraltet ist, wird von NMAKE Befehlsblock für die Abhängigkeit aufgerufen. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen abhängigen Elemente veraltet ist, wird von NMAKE zuerst hergeleitete abhängige aktualisiert. Weitere Informationen über hergeleitete abhängige Dateien finden Sie unter [Rückschlussregeln](../build/inference-rules.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abhängige Dateien](../build/dependents.md)
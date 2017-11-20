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
ms.openlocfilehash: eaf75c067b2e96e5ae4a893b56376bfc1b9bd1e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien
Eine hergeleitete abhängige eine Rückschlussregel abgeleitet wird und vor expliziten abhängigen Dateien ausgewertet wird. Wenn eine hergeleitete abhängige in Bezug auf ihr Ziel veraltet ist, wird von NMAKE Befehlsblock für die Abhängigkeit aufgerufen. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen abhängigen Elemente veraltet ist, wird von NMAKE zuerst hergeleitete abhängige aktualisiert. Weitere Informationen über hergeleitete abhängige Dateien finden Sie unter [Rückschlussregeln](../build/inference-rules.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abhängige Dateien](../build/dependents.md)
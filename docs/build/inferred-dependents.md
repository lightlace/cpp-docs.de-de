---
title: Hergeleitete abhängige Elemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a86ed1a8fe6c97ae11af50f59cb639ef6fd7c1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="inferred-dependents"></a>Hergeleitete abhängige Dateien
Eine hergeleitete abhängige eine Rückschlussregel abgeleitet wird und vor expliziten abhängigen Dateien ausgewertet wird. Wenn eine hergeleitete abhängige in Bezug auf ihr Ziel veraltet ist, wird von NMAKE Befehlsblock für die Abhängigkeit aufgerufen. Wenn eine hergeleitete abhängige nicht vorhanden ist oder in Bezug auf seine eigenen abhängigen Elemente veraltet ist, wird von NMAKE zuerst hergeleitete abhängige aktualisiert. Weitere Informationen über hergeleitete abhängige Dateien finden Sie unter [Rückschlussregeln](../build/inference-rules.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Abhängige Dateien](../build/dependents.md)
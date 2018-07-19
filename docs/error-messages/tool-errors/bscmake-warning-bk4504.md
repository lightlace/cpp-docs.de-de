---
title: BSCMAKE-Warnung BK4504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a17aa8b4e2a98d3bda5d21ea84962791b8051dc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295183"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE-Warnung BK4504
Datei enthält zu viele Verweise. Weitere Verweise von dieser Quelle ignoriert  
  
 Die CPP-Datei enthält mehr als 64.000 Symbolverweise. Wenn BSCMAKE 64.000 Verweise in einer Datei gefunden wurde, wird es alle weiteren Verweise ignoriert.  
  
 Zum Beheben des Problems teilen Sie die Datei in zwei oder mehr Dateien, von denen jede weniger als 64.000 hat Symbolverweise, oder verwenden Sie die `#pragma component(browser)` Präprozessordirektive Grenzwert Symbole, die für bestimmte Verweise generiert werden. Weitere Informationen finden Sie unter [Komponente](../../preprocessor/component.md).
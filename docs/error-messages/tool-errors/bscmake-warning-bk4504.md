---
title: BSCMAKE-Warnung BK4504 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK4504
dev_langs: C++
helpviewer_keywords: BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58a59b3141a8d7051aa7ece1bcb71dd960fabb18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE-Warnung BK4504
Datei enthält zu viele Verweise. Weitere Verweise von dieser Quelle ignoriert  
  
 Die CPP-Datei enthält mehr als 64.000 Symbolverweise. Wenn BSCMAKE 64.000 Verweise in einer Datei gefunden wurde, wird es alle weiteren Verweise ignoriert.  
  
 Zum Beheben des Problems teilen Sie die Datei in zwei oder mehr Dateien, von denen jede weniger als 64.000 hat Symbolverweise, oder verwenden Sie die `#pragma component(browser)` Präprozessordirektive Grenzwert Symbole, die für bestimmte Verweise generiert werden. Weitere Informationen finden Sie unter [Komponente](../../preprocessor/component.md).
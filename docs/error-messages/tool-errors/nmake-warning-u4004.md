---
title: 'NMAKE: Warnung U4004 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcbda9dd9d7ca5ecb99e46b9916fb95c2c560e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4004"></a>NMAKE: Warnung U4004
zu viele Regeln für Ziel "Zielname"  
  
 Blockieren von mehr als eine Beschreibung für das angegebene Ziel mit dem Doppelpunkt angegeben wurde (**:**) als Trennzeichen. NMAKE die Befehle in der ist der erste Beschreibungsblock ausgeführt und weitere Blöcke ignoriert.  
  
 Um dasselbe Ziel in mehrere Abhängigkeiten anzugeben, verwenden Sie zwei Doppelpunkten (`::`) als Trennzeichen in jeder Abhängigkeitszeile.
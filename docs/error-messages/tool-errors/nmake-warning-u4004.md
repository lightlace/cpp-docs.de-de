---
title: 'NMAKE: Warnung U4004 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 532abf2f62616d6e748c9a4e34f5c983f0853276
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317179"
---
# <a name="nmake-warning-u4004"></a>NMAKE: Warnung U4004
zu viele Regeln für Ziel "Zielname"  
  
 Blockieren von mehr als eine Beschreibung für das angegebene Ziel mit dem Doppelpunkt angegeben wurde (**:**) als Trennzeichen. NMAKE die Befehle in der ist der erste Beschreibungsblock ausgeführt und weitere Blöcke ignoriert.  
  
 Um dasselbe Ziel in mehrere Abhängigkeiten anzugeben, verwenden Sie zwei Doppelpunkten (`::`) als Trennzeichen in jeder Abhängigkeitszeile.
---
title: BSCMAKE-Warnung BK4504 | Microsoft-Dokumentation
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
ms.openlocfilehash: c8a2da8903dade37faf3b14175b65f3169efd908
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049766"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE-Warnung BK4504

Datei enthält zu viele Verweise. Weitere Verweise von dieser Quelle ignoriert

Die CPP-Datei enthält mehr als 64.000 Symbolverweise. Wenn BSCMAKE 64.000 Verweise in einer Datei aufgetreten ist, wird es alle weiteren Verweise ignoriert.

Um das Problem zu beheben, unterteilen Sie die Datei in zwei oder mehr Dateien, von denen jeder maximal 64.000 hat Symbolverweise, oder verwenden Sie die `#pragma component(browser)` Präprozessordirektive Limit-Symbole, die für bestimmte Verweise generiert werden. Weitere Informationen finden Sie unter [Komponente](../../preprocessor/component.md).
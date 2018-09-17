---
title: Pseudoziele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56c0c0c93163759b604352a6e623f15726b8e7ec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715831"
---
# <a name="pseudotargets"></a>Pseudoziele

Ein Pseudoziel handelt es sich um eine Bezeichnung, die anstelle eines Dateinamens in einer Abhängigkeitszeile verwendet. Sie wird als Datei interpretiert, die nicht vorhanden, und daher veraltet ist. NMAKE wird davon ausgegangen, dass ein Pseudoziel der Zeitstempel der letzten alle abhängigen Elemente ist. Wenn sie keine abhängigen Elemente verfügt, wird davon ausgegangen, dass die aktuelle Zeit. Wenn ein Pseudoziel als Ziel verwendet wird, werden die Befehle immer ausgeführt. Ein Pseudoziel als ein abhängiges Element verwendet, muss auch als Ziel in einer anderen Abhängigkeit angezeigt werden. Allerdings muss diese Abhängigkeit nicht um einen Befehlsblock zu erhalten.

Pseudoziel Namen führen Sie die Filename-Syntaxregeln für Ziele. Aber wenn der Name nicht mit eine Erweiterung verfügt (d. h. keinen Punkt enthält), sie können die 8-Zeichen-Grenze für Dateinamen überschreiten und kann bis zu 256 Zeichen lang sein.

## <a name="see-also"></a>Siehe auch

[Ziele](../build/targets.md)
---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1025'
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 8ecfc11f5cc991294d966a4b6c75d8da6669d5b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347206"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Ressourcencompiler: Schwerwiegender Fehler RW1025

Von heap-Arbeitsspeicher

Überprüfen Sie für Arbeitsspeicher-Software, die zu viel Speicherplatz beansprucht werden kann. Verwenden Sie das CHKDSK-Programm, um herauszufinden, wie viel Arbeitsspeicher, was man.

Wenn Sie eine umfangreiche Ressourcendatei erstellen, können Teilen Sie das Ressourcenskript in zwei Dateien auf. Verwenden Sie nach dem Erstellen von zwei RES-Dateien, die MS-DOS-Befehlszeile, um diese zu verknüpfen:

```
copy first.res /b + second.res /b full.res
```
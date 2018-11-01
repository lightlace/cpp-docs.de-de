---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1025'
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 8ecfc11f5cc991294d966a4b6c75d8da6669d5b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575681"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Ressourcencompiler: Schwerwiegender Fehler RW1025

Von heap-Arbeitsspeicher

Überprüfen Sie für Arbeitsspeicher-Software, die zu viel Speicherplatz beansprucht werden kann. Verwenden Sie das CHKDSK-Programm, um herauszufinden, wie viel Arbeitsspeicher, was man.

Wenn Sie eine umfangreiche Ressourcendatei erstellen, können Teilen Sie das Ressourcenskript in zwei Dateien auf. Verwenden Sie nach dem Erstellen von zwei RES-Dateien, die MS-DOS-Befehlszeile, um diese zu verknüpfen:

```
copy first.res /b + second.res /b full.res
```
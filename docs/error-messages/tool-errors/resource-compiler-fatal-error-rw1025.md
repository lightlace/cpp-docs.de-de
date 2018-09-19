---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1025 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bf7bdeed320c004ffb75fa1d25d9b89147b0c13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117399"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Ressourcencompiler: Schwerwiegender Fehler RW1025

Von heap-Arbeitsspeicher

Überprüfen Sie für Arbeitsspeicher-Software, die zu viel Speicherplatz beansprucht werden kann. Verwenden Sie das CHKDSK-Programm, um herauszufinden, wie viel Arbeitsspeicher, was man.

Wenn Sie eine umfangreiche Ressourcendatei erstellen, können Teilen Sie das Ressourcenskript in zwei Dateien auf. Verwenden Sie nach dem Erstellen von zwei RES-Dateien, die MS-DOS-Befehlszeile, um diese zu verknüpfen:

```
copy first.res /b + second.res /b full.res
```
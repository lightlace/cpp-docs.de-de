---
title: Schwerwiegender ML-Fehler A1017
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 6fb0835cca135fc994866dc2453734d7b3012a64
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856825"
---
# <a name="ml-fatal-error-a1017"></a>Schwerwiegender ML-Fehler A1017

**fehlender Quell Dateiname**

Von ml konnte keine Datei gefunden werden, die an den Linker assembliert oder übergeben werden soll.

Dieser Fehler wird generiert, wenn Sie ml-Befehlszeilenoptionen angeben, ohne einen Dateinamen anzugeben, der ausgeführt werden soll. Verwenden Sie die Befehlszeilenoption **/Ta** , um Dateien zu assemblieren, die keine ASM-Erweiterung haben.

Dieser Fehler kann auch durch Aufrufen von ml ohne Parameter generiert werden, wenn die ml-Umgebungsvariable Befehlszeilenoptionen enthält.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>
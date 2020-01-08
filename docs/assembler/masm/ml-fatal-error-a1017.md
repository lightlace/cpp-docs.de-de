---
title: Schwerwiegender ML-Fehler A1017
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 523fed26afae5a88c5f154283487d3453a2e48c7
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318058"
---
# <a name="ml-fatal-error-a1017"></a>Schwerwiegender ML-Fehler A1017

**fehlender Quell Dateiname**

Von ml konnte keine Datei gefunden werden, die an den Linker assembliert oder übergeben werden soll.

Dieser Fehler wird generiert, wenn Sie ml-Befehlszeilenoptionen angeben, ohne einen Dateinamen anzugeben, der ausgeführt werden soll. Verwenden Sie die Befehlszeilenoption **/Ta** , um Dateien zu assemblieren, die keine ASM-Erweiterung haben.

Dieser Fehler kann auch durch Aufrufen von ml ohne Parameter generiert werden, wenn die ml-Umgebungsvariable Befehlszeilenoptionen enthält.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](ml-error-messages.md)

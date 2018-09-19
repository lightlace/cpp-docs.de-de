---
title: 'NMAKE: Schwerwiegender Fehler U1051 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3d3a14b75a30aa22bcc9faafb97a218051bb080
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045015"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE: Schwerwiegender Fehler U1051

Nicht genügend Arbeitsspeicher

NMAKE: nicht genügend Arbeitsspeicher, einschließlich des virtuellen Speichers, da das Makefile zu groß oder komplex war.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Geben Sie auf dem Datenträger frei.

1. Erhöhen Sie die Größe der Auslagerungsdatei von Windows NT oder die Windows-Auslagerungsdatei.

1. Wenn nur ein Teil des Makefiles verwendet wird, teilen Sie dieses in separate Dateien auf, oder verwenden Sie **! IF** präprozessoranweisungen, um die Menge zu begrenzen, die NMAKE verarbeiten muss. Die **! IF** Includeanweisungen **! IF**, `!IFDEF`, **! IFNDEF**, **! ElseIf**, **! ANDERE** `IFDEF`, und **! ANDERE** `IFNDEF`.
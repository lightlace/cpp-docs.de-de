---
title: 'NMAKE: Schwerwiegender Fehler U1051'
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: ddf1d262fb8dfc6e63b0bf5cc098b7b140539310
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367199"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE: Schwerwiegender Fehler U1051

Nicht genügend Arbeitsspeicher

NMAKE: nicht genügend Arbeitsspeicher, einschließlich des virtuellen Speichers, da das Makefile zu groß oder komplex war.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Geben Sie auf dem Datenträger frei.

1. Erhöhen Sie die Größe der Auslagerungsdatei von Windows NT oder die Windows-Auslagerungsdatei.

1. Wenn nur ein Teil des Makefiles verwendet wird, teilen Sie dieses in separate Dateien auf, oder verwenden Sie **! IF** präprozessoranweisungen, um die Menge zu begrenzen, die NMAKE verarbeiten muss. Die **! IF** Includeanweisungen **! IF**, `!IFDEF`, **! IFNDEF**, **! ElseIf**, **! ANDERE** `IFDEF`, und **! ANDERE** `IFNDEF`.
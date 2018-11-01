---
title: 'Ressourcencompiler: Schwerwiegender Fehler RC1015'
ms.date: 11/04/2016
f1_keywords:
- RC1015
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
ms.openlocfilehash: f20101c2edc4da132c89dcda451c71af2304a13d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552216"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Ressourcencompiler: Schwerwiegender Fehler RC1015

Includedatei 'Dateiname' kann nicht geöffnet werden

Die angegebenen Include-Datei ist nicht vorhanden, konnte nicht geöffnet werden oder wurde nicht gefunden.

Stellen Sie sicher, dass die Umgebungseinstellungen gültig sind und der richtige Pfad für die Datei angegeben wurde. Stellen Sie sicher, dass genügend Dateihandles Ressourcencompiler zur Verfügung stehen. Ist die Datei auf einem Netzlaufwerk, stellen Sie sicher, dass Sie über Berechtigungen zum Öffnen der Datei verfügen.

RC1015 kann auch auftreten, wenn die Include-Datei vorhanden, in einem Verzeichnis ist als zusätzliches Includeverzeichnis in den Konfigurationseigenschaften -> Ressourcen angegeben -> Eigenschaftenseite "Allgemein"; Geben Sie den vollständigen Pfad zur Include-Datei.

---
title: Linkertoolwarnung LNK4099 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50bdceaba2e72312febec4819b96df334b5398c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026000"
---
# <a name="linker-tools-warning-lnk4099"></a>Linkertoolwarnung LNK4099

PDB-Datei 'Dateiname' wurde nicht mit 'Objektbibliothek' oder 'Path'; gefunden. Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Der Linker konnte Ihre PDB-Datei zu suchen. Kopieren Sie ihn in das Verzeichnis mit `object/library`.

Der Name der Objektdatei zugeordnete PDB-Datei zu finden:

1. Extrahieren Sie eine Objektdatei, aus der Bibliothek mit [Lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**obj** `xyz` **lib**.

1. Überprüfen Sie den Pfad zur PDB-Datei mit **Dumpbin/section:.Debug$ T/RAWDATA** `objectname` **obj**.

Sie könnten auch kompilieren Sie mit ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), sodass die PDB-Datei muss nicht verwendet werden, oder entfernen Sie die [/DEBUG](../../build/reference/debug-generate-debug-info.md) Linkeroption, wenn Sie PDB-Dateien für die Objekte keine verknüpfen.
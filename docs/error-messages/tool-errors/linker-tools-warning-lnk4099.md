---
title: Linkertoolwarnung LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: dcf4d44c3a0b5b10035af763040c2912afc8c6f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310889"
---
# <a name="linker-tools-warning-lnk4099"></a>Linkertoolwarnung LNK4099

PDB-Datei 'Dateiname' wurde nicht mit 'Objektbibliothek' oder 'Path'; gefunden. Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Der Linker konnte Ihre PDB-Datei zu suchen. Kopieren Sie ihn in das Verzeichnis mit `object/library`.

Der Name der Objektdatei zugeordnete PDB-Datei zu finden:

1. Extrahieren Sie eine Objektdatei, aus der Bibliothek mit [Lib](../../build/reference/lib-reference.md) **/extract:**`objectname`**obj** `xyz` **lib**.

1. Überprüfen Sie den Pfad zur PDB-Datei mit **Dumpbin/section:.Debug$ T/RAWDATA** `objectname` **obj**.

Sie könnten auch kompilieren Sie mit ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), sodass die PDB-Datei muss nicht verwendet werden, oder entfernen Sie die [/DEBUG](../../build/reference/debug-generate-debug-info.md) Linkeroption, wenn Sie PDB-Dateien für die Objekte keine verknüpfen.
---
title: Erstellen einer BSC-Datei mit BSCMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 053bc7565accce5db8998ae8efec256ef37d37b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442587"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>Erstellen einer BSC-Datei mit BSCMAKE

BSCMAKE erstellt oder neu erstellt eine BSC-Datei in die effizienteste Methode, die dies möglich. Um potenzielle Probleme zu vermeiden, ist es wichtig zu verstehen, des Buildprozesses.

Wenn BSCMAKE eine Browseinformationsdatei erstellt wird, schneidet die SBR-Dateien, um die Länge Null. Während eines nachfolgende Builds der gleichen Datei weist eine Zeichenfolge der Länge Null (oder leer) SBR-Datei BSCMAKE, dass die SBR-Datei keine neue Beiträge enthält. Sie können BSCMAKE wissen, dass ein Update dieses Teils der Datei nicht erforderlich ist, und ein inkrementelles Builds wird ausreichend sein. Bei jedem Build (es sei denn, die/n-Option angegeben ist), BSCMAKE zuerst versucht, inkrementell aktualisieren Sie die Datei mit der nur die SBR-Dateien, die geändert wurden.

BSCMAKE sucht nach einer BSC-Datei, die den Namen, die mit der/o-Option angegeben hat. Wenn/o nicht angegeben ist, sucht BSCMAKE für eine Datei mit dem Basisnamen der ersten SBR-Datei und der Erweiterung BSC. Wenn die Datei vorhanden ist, führt BSCMAKE als inkrementellen Build des der Browserinformationsdatei mithilfe der zugehörigen SBR-Dateien. Wenn die Datei nicht vorhanden ist, wird ein vollständiger Build, der alle .sbr-Dateien mithilfe von BSCMAKE ausgeführt. Die Regeln für Builds sind wie folgt aus:

- Für einen vollständigen Build erfolgreich ausgeführt werden kann alle angegebenen SBR-Dateien müssen vorhanden sein und müssen nicht abgeschnitten werden. Wenn eine SBR-Datei abgeschnitten ist, müssen Sie es neu erstellen (durch erneutes kompilieren oder Assemblieren) vor der Ausführung von BSCMAKE.

- Für einen inkrementellen Build erfolgreich ausgeführt werden kann muss die BSC-Datei vorhanden sein. Alle zugehörigen .sbr-Dateien, sogar leere Dateien, muss vorhanden sein und muss in der BSCMAKE-Befehlszeile angegeben werden. Wenn Sie eine SBR-Datei über die Befehlszeile weglassen, wird BSCMAKE seinen Beitrag aus der Datei entfernt.

## <a name="see-also"></a>Siehe auch

[Erstellen einer BSC-Datei](../../build/reference/building-a-dot-bsc-file.md)
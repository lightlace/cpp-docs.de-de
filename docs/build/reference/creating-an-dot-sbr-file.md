---
title: Erstellen einer SBR-Datei
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 75c3b926a605de66c876e9350218807031cd9a43
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810405"
---
# <a name="creating-an-sbr-file"></a>Erstellen einer SBR-Datei

Die Eingabedateien für BSCMAKE sind SBR-Dateien. Der Compiler erstellt eine SBR-Datei für die einzelnen Objektdateien (obj) kompiliert. Wenn Sie erstellen oder aktualisieren Ihre Browseinformationsdatei, müssen alle .sbr-Dateien für Ihr Projekt auf dem Datenträger verfügbar sein.

Geben Sie zum Erstellen einer SBR-Datei mit allen möglichen Informationen [/FR](fr-fr-create-dot-sbr-file.md).

Geben Sie zum Erstellen einer SBR-Datei, die keine lokale Symbole enthält [/FR](fr-fr-create-dot-sbr-file.md). Wenn die SBR-Dateien auf lokalen Symbole enthalten, Sie können weiterhin wegzulassen in der BSC-Datei mithilfe von BSCMAKE [El-Option](bscmake-options.md)`.`

Sie können eine SBR-Datei erstellen, ohne dass eine vollständige Kompilierung ausgeführt. Beispielsweise können Sie angeben, die/ZS-Option aus, um den Compiler an, führen Sie eine Überprüfung der Syntax und weiterhin eine SBR-Datei generieren, wenn Sie/fr oder /Fr. angeben

Der Buildprozess möglich effizienter, wenn zunächst die SBR-Dateien gepackt werden, um nicht referenzierte Definitionen zu entfernen. Der Compiler packt automatisch SBR-Dateien.

## <a name="see-also"></a>Siehe auch

[Erstellen einer BSC-Datei](building-a-dot-bsc-file.md)

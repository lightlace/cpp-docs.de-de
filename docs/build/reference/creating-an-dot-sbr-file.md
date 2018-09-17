---
title: Erstellen einer. SBR-Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac872dd13458c3fe15971f30a72b06e5510c5bd0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723683"
---
# <a name="creating-an-sbr-file"></a>Erstellen einer SBR-Datei

Die Eingabedateien für BSCMAKE sind SBR-Dateien. Der Compiler erstellt eine SBR-Datei für die einzelnen Objektdateien (obj) kompiliert. Wenn Sie erstellen oder aktualisieren Ihre Browseinformationsdatei, müssen alle .sbr-Dateien für Ihr Projekt auf dem Datenträger verfügbar sein.

Geben Sie zum Erstellen einer SBR-Datei mit allen möglichen Informationen [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).

Geben Sie zum Erstellen einer SBR-Datei, die keine lokale Symbole enthält [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md). Wenn die SBR-Dateien auf lokalen Symbole enthalten, Sie können weiterhin wegzulassen in der BSC-Datei mithilfe von BSCMAKE [El-Option](../../build/reference/bscmake-options.md)`.`

Sie können eine SBR-Datei erstellen, ohne dass eine vollständige Kompilierung ausgeführt. Beispielsweise können Sie angeben, die/ZS-Option aus, um den Compiler an, führen Sie eine Überprüfung der Syntax und weiterhin eine SBR-Datei generieren, wenn Sie/fr oder /Fr. angeben

Der Buildprozess möglich effizienter, wenn zunächst die SBR-Dateien gepackt werden, um nicht referenzierte Definitionen zu entfernen. Der Compiler packt automatisch SBR-Dateien.

## <a name="see-also"></a>Siehe auch

[Erstellen einer BSC-Datei](../../build/reference/building-a-dot-bsc-file.md)
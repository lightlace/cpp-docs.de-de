---
title: Erstellen einer. SBR-Datei | Microsoft Docs
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
ms.openlocfilehash: bdada1f4d07d02988da388e39e332c832f633adb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="creating-an-sbr-file"></a>Erstellen einer SBR-Datei
Die Eingabedateien für BSCMAKE sind SBR-Dateien. Der Compiler erstellt eine SBR-Datei für die einzelnen Objektdateien (.obj) kompiliert. Beim Erstellen oder aktualisieren Ihre Browseinformationsdatei müssen alle SBR-Dateien für Ihr Projekt auf dem Datenträger verfügbar sein.  
  
 Geben Sie zum Erstellen einer SBR-Datei mit allen möglichen Informationen [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Geben Sie zum Erstellen einer SBR-Datei, die keine lokalen Symbole enthält [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md). Wenn die SBR-Dateien lokale Symbole enthalten, Sie können weiterhin sie auslassen von BSC-Datei mithilfe von BSCMAKE  [ /El-Option](../../build/reference/bscmake-options.md)`.`  
  
 Sie können eine SBR-Datei erstellen, ohne eine vollständige Kompilierung auszuführen. Beispielsweise können Sie angeben, die/ZS-Option aus, um den Compiler an, überprüfen Sie die Syntax und generieren weiterhin eine SBR-Datei aus, wenn Sie/fr oder /Fr. angeben  
  
 Während des Erstellungsprozesses kann effizienter, wenn zunächst die SBR-Dateien gepackt werden, um Unreferenzierte Definitionen zu entfernen. Der Compiler packs automatisch SBR-Dateien.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer BSC-Datei](../../build/reference/building-a-dot-bsc-file.md)
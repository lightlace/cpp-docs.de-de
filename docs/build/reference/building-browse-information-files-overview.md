---
title: "Erstellung von Browserinformationsdateien: Übersicht über die | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5b369d5a708e0ee56df635234c68ee88a31af48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="building-browse-information-files-overview"></a>Erstellen von Browseinformationsdateien: Übersicht
Um Browserinformationen für die Symbolsuche zu erstellen, erstellt der Compiler eine SBR-Datei für jede Quelldatei in Ihrem Projekt, klicken Sie dann BSCMAKE an. EXE-Datei wird die SBR-Dateien in einer BSC-Datei.  
  
 Generieren von SBR- und BSC-Dateien dauert einige Zeit, damit Visual C++ diese Funktionen standardmäßig deaktiviert. Wenn Sie aktuelle Informationen durchsuchen möchten, müssen Sie die Optionen zum Durchsuchen aktivieren und erstellen Sie das Projekt erneut.  
  
 Verwendung [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) oder [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) an den Compiler aufzufordern, SBR-Dateien zu erstellen. Um BSC-Dateien zu erstellen, rufen Sie [BSCMAKE](../../build/reference/bscmake-command-line.md) über die Befehlszeile. Mithilfe von BSCMAKE über die Befehlszeile bietet Ihnen eine genauere Kontrolle über die Manipulation von Browserinformationsdateien. Finden Sie unter [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md) für Weitere Informationen.  
  
> [!TIP]
>  Sie können einschalten SBR-Datei generieren jedoch BSC-Datei Generation deaktiviert lassen. Dies bietet schnelle erstellt, aber auch ermöglicht es Ihnen, eine neue .bsc-Datei erstellen Sie schnell durch Aktivieren der Generierung von BSC-Dateien und beim Erstellen des Projekts.  
  
 Sie können die Zeit, Speicher und Speicherplatz erforderlich, um eine BSC-Datei zu erstellen, durch das Reduzieren der Größe der BSC-Datei reduzieren.  
  
 Finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md) Informationen zum Erstellen einer Browserdatei in der Entwicklungsumgebung.  
  
### <a name="to-create-a-smaller-bsc-file"></a>So erstellen eine kleinere BSC-Datei  
  
1.  Verwendung [BSCMAKE-Befehlszeilenoptionen](../../build/reference/bscmake-options.md) Ausschließen von Informationen aus der Browserinformationsdatei aus.  
  
2.  Lassen Sie lokale Symbole in eine oder mehrere .sbr-Dateien beim Kompilieren oder assemblieren.  
  
3.  Wenn eine Objektdatei keine für die aktuelle Phase des Debuggens erforderlichen Informationen enthält, geben Sie die SBR-Datei von BSCMAKE-Befehl, beim Neuerstellen der Browserinformationsdatei.  
  
### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>Kombinieren von Suchinformationen aus mehreren Projekten in einem Browsedatei (.bsc)  
  
1.  Entweder nicht erstellen Sie die BSC-Datei auf Projektebene oder verwenden Sie den Schalter/n, um zu verhindern, dass die SBR-Dateien abgeschnitten wird.  
  
2.  Nachdem alle Projekte erstellt werden, führen Sie BSCMAKE mit allen SBR-Dateien als Eingabe. Platzhalter sind zulässig. Für die Instanz, wenn Sie Projektverzeichnisse C:\X C:\Y und C:\Z SBR-Dateien, und wollten sie alle in einer BSC-Datei kombinieren Sie hatten, verwenden Sie BSCMAKE C:\X\\*.sbr C:\Y\\\*SBR C:\Z\\\*. SBR/o c:\whatever_directory\combined.bsc zum Erstellen der kombinierten BSC-Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)
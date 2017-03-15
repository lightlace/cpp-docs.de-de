---
title: "Erstellen von Browseinformationsdateien: &#220;bersicht | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSC-Dateien, Informationen über .bsc-Dateien"
  - "Browserinformationsdateien (.bsc)"
  - "Browserinformationsdateien (.bsc), Erstellen"
  - "BSC-Dateien, Informationen über BSC-Dateien"
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erstellen von Browseinformationsdateien: &#220;bersicht
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Um Browserinformationen für die Symbolsuche zu erstellen, legt der Compiler für jede Quelldatei in einem Projekt eine SBR\-Datei an, die dann von BSCMAKE.EXE zu einer BSC\-Datei verknüpft werden.  
  
 Das Generieren von SBR\- und BSC\-Dateien erfordert Zeit und ist deshalb bei Visual C\+\+ standardmäßig deaktiviert.  Wenn Sie aktuelle Informationen durchsuchen möchten, müssen Sie die Anzeigeoptionen wieder aktivieren und das Projekt erneut erstellen.  
  
 Verwenden Sie [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) oder [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md), um mithilfe des Compilers SBR\-Dateien zu erstellen.  Rufen Sie [BSCMAKE](../../build/reference/bscmake-command-line.md) von der Befehlszeile auf, um BSC\-Dateien zu erstellen.  Der Aufruf von BSCMAKE von der Befehlszeile aus ermöglicht Ihnen eine genauere Steuerung der Änderung von Browserinformationsdateien.  Weitere Informationen erhalten Sie in der [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md).  
  
> [!TIP]
>  Sie können die Generierung von SBR\-Dateien aktivieren, die Erstellung von BSC\-Dateien jedoch deaktiviert lassen.  Dadurch können die Dateien schnell erstellt werden, Sie können jedoch auch durch Aktivieren der Generierung von BSC\-Dateien und das Erstellen des Projekts schnell eine neue BSC\-Datei anlegen.  
  
 Wenn eine BSC\-Datei verkleinert wird, sind weniger Zeit, Arbeitsspeicher und Festplattenspeicher für das Erstellen der BSC\-Datei erforderlich.  
  
 Weitere Informationen darüber, wie Sie eine Browserdatei in der Entwicklungsumgebung erstellen, finden Sie unter [Eigenschaftenseite "Allgemein"\(Projekt\)](../../ide/general-property-page-project.md).  
  
### So erstellen Sie eine kleinere BSC\-Datei  
  
1.  Verwenden Sie die [BSCMAKE\-Befehlszeilenoptionen](../../build/reference/bscmake-options.md), um bestimmte Informationen aus der Browserinformationsdatei auszuschließen.  
  
2.  Geben Sie beim Kompilieren oder Assemblieren lokale Symbole nicht in einer SBR\-Datei oder mehreren SBR\-Dateien an.  
  
3.  Wenn eine Objektdatei keine Informationen enthält, die im aktuellen Schritt des Debugvorgangs benötigt werden, geben Sie die entsprechende SBR\-Datei in dem BSCMAKE\-Befehl nicht an, wenn Sie die Browserinformationsdatei neu erstellen.  
  
### So kombinieren Sie Browserinformationen von mehreren Projekten in einer Browsedatei \(.bsc\)  
  
1.  Erstellen Sie keine BSC\-Datei auf Projektebene. Verwenden Sie andernfalls den \/n\-Schalter, um zu vermeiden, dass die SBR\-Dateien abgeschnitten werden.  
  
2.  Nachdem alle Projekte erstellt wurden, führen Sie BSCMAKE mit allen SBR\-Dateien als Eingabe aus.  Die Eingabe von Platzhaltern ist möglich.  Wenn Sie z. B. die SBR\-Dateien in den Projektverzeichnissen C:\\X, C:\\Y und C:\\Z zu einer BSC\-Datei kombinieren möchten, verwenden Sie BSCMAKE C:\\X\\\*.sbr C:\\Y\\\*.sbr C:\\Z\\\*.sbr \/o c:\\beliebiger\_Pfad\\kombiniert.bsc, um die kombinierte BSC\-Datei zu erstellen.  
  
## Siehe auch  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)   
 [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md)
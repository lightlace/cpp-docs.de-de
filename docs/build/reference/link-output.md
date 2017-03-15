---
title: "LINK-Ausgabe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ilk-Dateien"
  - "DLLs [C++], Als Linkerausgabe"
  - "Ausführbare Dateien [C++], Als Linkerausgabe"
  - "Dateien [C++], LINK"
  - "ILK-Dateien"
  - "Importbibliotheken [C++], Erstellen"
  - "LINK-Tool [C++], Zuordnungsdatei"
  - "LINK-Tool [C++], Ausgabe"
  - "Linker [C++], Ausgabedateien"
  - "Zuordnungsdateien [C++]"
  - "Zuordnungsdateien [C++], LINK-Ausgabe"
  - "Ausgabedateien [C++], Linker"
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# LINK-Ausgabe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Ausgabe von **LINK** erstreckt sich auf EXE\-Dateien, DLLs, MAP\-Dateien und Meldungen.  
  
##  <a name="_core_output_files"></a> Ausgabedateien  
 Die Standardausgabedatei von **LINK** ist eine EXE\-Datei.  Wenn die Option [\/DLL](../../build/reference/dll-build-a-dll.md) angegeben wurde, erstellt **LINK** eine DLL\-Datei.  Sie können den Namen der Ausgabedatei über die Option [\/OUT \(Ausgabedateiname\)](../../build/reference/out-output-file-name.md) steuern.  
  
 Im inkrementellen Modus erstellt **LINK** eine ILK\-Datei zum Speichern von Statusinformationen, die bei späteren inkrementellen Erstellungsvorgängen des Programms verwendet werden.  Weitere Informationen zu ILK\-Dateien finden Sie unter [ILK\-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md).  Weitere Informationen über das inkrementelle Verknüpfen finden Sie unter der Option [\/INCREMENTAL \(Inkrementell verknüpfen\)](../../build/reference/incremental-link-incrementally.md).  
  
 Wenn **LINK** ein Programm erstellt, das Exporte enthält \(in der Regel eine DLL\), wird auch eine LIB\-Datei erstellt, sofern im Erstellungsvorgang keine EXP\-Datei verwendet wurde.  Sie können den Dateinamen für die Importbibliothek über die Option [\/IMPLIB](../../build/reference/implib-name-import-library.md) steuern.  
  
 Wenn die Option [\/MAP \(Zuordnungsdatei generieren\)](../../build/reference/map-generate-mapfile.md) angegeben wurde, erstellt **LINK** eine MAP\-Datei.  
  
 Wenn die Option [\/DEBUG \(Debuginfo generieren\)](../../build/reference/debug-generate-debug-info.md) angegeben wurde, erstellt **LINK** eine PDB\-Datei für die Debug\-Informationen des Programms.  
  
##  <a name="_core_other_output"></a> Andere Ausgabe  
 Wenn Sie in der Befehlszeile ohne weitere Zusätze `link` eingeben, zeigt **LINK** einen Verwendungshinweis mit Angabe aller Optionen an.  
  
 **LINK** zeigt eine Meldung mit Copyright\- und Versionsinformationen an und gibt die Befehlsdateieingabe wieder, sofern nicht die Option [\/NOLOGO \(Startbanner unterdrücken\)](../../build/reference/nologo-suppress-startup-banner-linker.md) verwendet wird.  
  
 Sie können die Option [\/VERBOSE \(Statusmeldungen ausgeben\)](../../build/reference/verbose-print-progress-messages.md) verwenden, um zusätzliche Einzelheiten über den Erstellungsvorgang anzuzeigen.  
  
 **LINK** gibt Fehler\- und Warnmeldungen in der Form LNK*nnnn* aus.  Dieser Fehlerpräfix und der Zahlenbereich werden ebenfalls von **LIB**, **DUMPBIN** und **EDITBIN** verwendet.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
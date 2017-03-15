---
title: "Ressourcencompiler: Fehler RW2003 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2003"
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Fehler RW2003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellungsfehler  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  **Fehler: Bitmapdatei entspricht nicht 3.00\-Format**  
  
     Bitmaps im Format von Windows, Version 2.x, können nicht in Ressourcendateien der Version 3.x verwendet werden.  Die Bitmap muss neu gezeichnet oder in das 3.x\-Format konvertiert werden.  
  
2.  **Fehler: Alte DIB im Ressourcennamen.  Verwenden Sie SDKPAINT.**  
  
     Eine Device Indipendent Bitmap \(DIB\) in der angegebenen Ressource ist nicht mit dem Format von Windows 3.0 kompatibel.  Die Bitmap muss neu gezeichnet oder in das 3.x\-Format konvertiert werden.  
  
3.  **Fehler: Ressourcendatei entspricht nicht 3.00\-Format**  
  
     Das Format einer früheren Version von Windows wurde vom Symbol oder Cursor in der angegebenen Ressource verwendet.  Das Symbol oder der Cursor muss neu gezeichnet oder in das 3.x\-Format konvertiert werden.  
  
4.  **Unbekanntes DIB\-Headerformat**  
  
     Der Bitmapheader enthält keine BITMAPCOREHEADER\-Struktur oder BITMAPINFOHEADER\-Struktur.  
  
5.  **Symbolinformationen können nicht initialisiert werden**  
  
     Dieser Fehler tritt nur in Visual C\+\+ auf.  Er wird möglicherweise dadurch verursacht, dass zu viele Dateien geöffnet sind oder die Datendateien, die für Visual C\+\+ benötigt werden, um die Symbole in das Skript zu importieren, nicht geöffnet werden können oder nicht in sie geschrieben werden kann.  Es wird versucht, diese Dateien in dem Verzeichnis, das in der **TMP**\-Umgebungsvariablen angegeben ist, oder, falls kein temporäres Verzeichnis angegeben ist, im aktuellen Verzeichnis zu erstellen.  
  
6.  **Symbolinformationen können nicht gespeichert werden**  
  
     Dieser Fehler tritt nur in Visual C\+\+ auf.  Er wird möglicherweise dadurch verursacht, dass zu viele Dateien geöffnet sind oder die Datendateien, die für Visual C\+\+ benötigt werden, um die Symbole in das Skript zu importieren, nicht geschlossen werden können oder nicht in sie geschrieben werden kann.  Es wird versucht, diese Dateien in dem Verzeichnis, das in der **TMP**\-Umgebungsvariablen angegeben ist, oder, falls kein temporäres Verzeichnis angegeben ist, im aktuellen Verzeichnis zu verwenden.  
  
7.  **Bitmapdatei entspricht nicht 2.03\-Format**  
  
     Es wurde ein Format einer früheren Version als Version 2.03 von einer Bitmap verwendet.  Die Bitmap muss neu gezeichnet oder in das Format für Version 3.00 oder eine höhere Version konvertiert werden.  
  
8.  **Ressource ist zu groß.**  
  
     Ressourcendateien dürfen unter Windows 3.1 ungefähr 65.000 Bytes nicht überschreiten.  Ressourcendateien, die diese Grenze überschreiten, können weder mit Visual C\+\+ noch mit dem Befehlszeilen\-Ressourcencompiler kompiliert werden.  Diese Grenze betrifft nicht Cursor, Symbole, Bitmaps oder andere dateibasierte Ressourcen.  
  
9. **Ressourcendatei entspricht nicht 3.00\-Format**  
  
     Es wurde das Format einer früheren Version als Version 3.00 von einem Cursor oder einem Symbol verwendet.  Die Ressource muss in das Format für Version 3.00 oder eine höhere Version konvertiert oder neu gezeichnet werden.  
  
10. **Temporäre Datei kann nicht geöffnet werden**  
  
     Eine temporäre Datei konnte vom Ressourcencompiler\/Visual C\+\+ nicht geöffnet werden.  Möglicherweise besitzen Sie keine Schreibberechtigung für das Verzeichnis, oder das Verzeichnis ist nicht vorhanden.  Es wird versucht, diese Dateien in dem Verzeichnis, das in der **TMP**\-Umgebungsvariablen angegeben ist, oder, falls kein temporäres Verzeichnis angegeben ist, im aktuellen Verzeichnis zu verwenden.
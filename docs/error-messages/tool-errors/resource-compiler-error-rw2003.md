---
title: 'Ressourcencompiler: Fehler RW2003 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW2003
dev_langs:
- C++
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f388ca21d95e7d675a6b9890a7368765b5c0d7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2003"></a>Ressourcencompiler: Fehler RW2003
Generation-Fehler  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  **Fehler:-Bitmapdatei ist nicht 3.00-Format**  
  
     Bitmaps mit dem Windows-Version 2.x-Format können nicht in Ressourcendateien der Version 3.x verwendet werden. Die Bitmap muss neu gezeichnet oder in das 3.x-Format konvertiert werden.  
  
2.  **Fehler: Alte DIB im Ressourcenname. SDKPAINT durchlaufen**  
  
     Ein Gerät Independent Bitmap (DIB) in die angegebene Ressource ist nicht kompatibel mit dem Windows-3.0-Format. Die Bitmap muss neu gezeichnet oder in das 3.x-Format konvertiert werden.  
  
3.  **Fehler: Ressourcen-Dateiname-Ressource ist nicht 3.00-Format**  
  
     Ein Symbol oder Cursor in die angegebene Ressource verwendet ein Format aus einer früheren Version von Windows. Das Symbol oder Cursor muss neu gezeichnet oder in das 3.x-Format konvertiert werden.  
  
4.  **Unbekannte DIB-Headerformat**  
  
     Die Bitmapheader ist keine enthält oder BITMAPINFOHEADER Struktur.  
  
5.  **Kann nicht zum Initialisieren von Symbolinformationen**  
  
     Dieser Fehler tritt nur in Visual C++. Die wahrscheinlichste Ursache ist, dass Sie zu viele Dateien geöffnet haben, oder Sie können nicht geöffnet oder Schreiben auf die Datendateien für Visual C++, um die Symbole in Ihrem Skript importieren benötigt. Visual C++ zur Erstellung dieser Dateien im Verzeichnis angegeben werden, indem versucht die **TMP** -Umgebungsvariablen oder das aktuelle Verzeichnis, falls keiner angegeben ist.  
  
6.  **Kann nicht gespeichert werden Symbolinformationen**  
  
     Dieser Fehler tritt nur in Visual C++. Die wahrscheinlichste Ursache ist, dass Sie zu viele Dateien geöffnet haben, oder Sie nicht geschlossen oder Schreiben auf die Datendateien für Visual C++, um die Symbole in Ihrem Skript importieren benötigt. Visual C++ versucht, verwenden Sie diese Dateien in das Verzeichnis, das gemäß der **TMP** -Umgebungsvariablen oder das aktuelle Verzeichnis, falls keiner angegeben ist.  
  
7.  **Bitmapdatei ist nicht 2.03-Format**  
  
     Für eine Bitmap wurde ein Format einer früheren Version als Version 2.03 verwendet. Die Bitmap muss neu gezeichnet oder in das Format für Version 3.00 oder eine höhere Version konvertiert werden.  
  
8.  **Ressource ist zu groß**  
  
     Für Windows 3.1 eine Ressource ungefähr 65.000 Bytes nicht überschreiten darf. Wenn die Ressource der Fall ist, wird nicht können mit Visual C++ oder der Befehlszeile Ressourcencompiler kompiliert werden. Dieser Grenzwert gilt nicht für Cursor, Symbole, Bitmaps oder andere dateibasierte Ressourcen.  
  
9. **Ressourcendatei ist nicht 3.00-Format**  
  
     Ein Cursor oder Symbol verwendet Format vor Version 3.00. Die Ressource muss konvertierte oder neu gezeichnet, mit dem Format für Version 3.00 oder höher sein.  
  
10. **Temporäre Datei konnte nicht geöffnet**  
  
     Der Ressourcencompiler/Visual C++ konnte eine temporäre Datei nicht öffnen. Die wahrscheinlichste Ursache ist, dass Sie nicht über Schreibberechtigungen für das Verzeichnis verfügen oder dass das Verzeichnis nicht vorhanden ist. Der Ressourcencompiler/Visual C++ versucht, diese Dateien im von der **TMP** -Umgebungsvariablen angegebenen Verzeichnis bzw. im aktuellen Verzeichnis zu verwenden, wenn kein Verzeichnis angegeben ist.
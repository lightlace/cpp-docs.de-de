---
title: 'Ressourcencompiler: Fehler RW2003 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2003
dev_langs:
- C++
helpviewer_keywords:
- RW2003
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84f539a42e3613fb3cb909af61ac6eb867d7d887
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071403"
---
# <a name="resource-compiler-error-rw2003"></a>Ressourcencompiler: Fehler RW2003

Fehler bei der skriptgenerierung

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. **Fehler:-Bitmapdatei ist nicht 3.00-Format**

   Bitmaps mit dem Windows-Version 2.x-Format können nicht in Ressourcendateien der Version 3.x verwendet werden. Die Bitmap muss neu gezeichnet oder 3.x-Format konvertiert werden.

1. **Fehler: Die alte DIB im Ressourcennamen. SDKPAINT durchlaufen**

   Ein Gerät Independent Bitmap (DIB) in der angegebenen Ressource ist nicht kompatibel mit dem Windows-3.0-Format. Die Bitmap muss neu gezeichnet oder in das 3.x-Format konvertiert werden.

1. **Fehler: Datei Resource-Ressourcenname ist nicht 3.00-Format**

   Ein Symbol oder Cursor in die angegebene Ressource wird das Format von einer früheren Version von Windows verwendet. Das Symbol oder Cursor muss neu gezeichnet oder in das 3.x-Format konvertiert werden.

1. **Unbekannter DIB-Headerformat**

   Die Bitmapheader ist keiner Struktur enthält oder BITMAPINFOHEADER.

1. **Kann nicht initialisiert werden Symbolinformationen**

   Dieser Fehler tritt nur in Visual C++. Die wahrscheinlichste Ursache ist, dass zu viele geöffnete Dateien oder Sie können nicht geöffnet oder Schreiben in die Datendateien für Visual C++, um die Symbole in Ihrem Skript importieren benötigt. Visual C++ versucht, zum Erstellen dieser Dateien in das Verzeichnis, das gemäß der **TMP** Umgebungsvariablen oder im aktuellen Verzeichnis, wenn keine Angabe erfolgt.

1. **Kann nicht zum Speichern von Symbolinformationen**

   Dieser Fehler tritt nur in Visual C++. Die wahrscheinlichste Ursache ist, dass zu viele geöffnete Dateien oder Sie können nicht schließen, oder Schreiben in die Datendateien für Visual C++, um die Symbole in Ihrem Skript importieren benötigt. Visual C++ versucht, diese Dateien im angegebenen Verzeichnis die **TMP** Umgebungsvariablen oder im aktuellen Verzeichnis, wenn keine Angabe erfolgt.

1. **Bitmapdatei ist nicht 2.03-Format**

   Für eine Bitmap wurde ein Format einer früheren Version als Version 2.03 verwendet. Die Bitmap muss neu gezeichnet oder in das Format für Version 3.00 oder eine höhere Version konvertiert werden.

1. **Ressource ist zu groß**

   Für Windows 3.1 darf eine Ressource mit ungefähr 65.000 Bytes nicht überschreiten. Wenn die Ressource der Fall ist, klicken Sie dann werden Sie nicht können sie mit Visual C++- oder der Befehlszeile Ressourcencompiler kompiliert. Dieser Grenzwert gilt nicht für Cursor, Symbole, Bitmaps oder andere dateibasierte Ressourcen.

9. **Ressourcendatei entspricht nicht 3.00-Format**

   Ein Cursor oder ein Symbol für verwendet das Format vor der Version 3.00. Die Ressource muss konvertiert oder neu gezeichnet, mit dem Format der Version 3.00 oder höher sein.

10. **Temporäre Datei kann nicht geöffnet**

   Der Ressourcencompiler/Visual C++ konnte eine temporäre Datei nicht öffnen. Die wahrscheinlichste Ursache ist, dass Sie nicht über Schreibberechtigungen für das Verzeichnis verfügen oder ein Verzeichnis nicht vorhanden ist. Der Ressourcencompiler/Visual C++ versucht, diese Dateien im von der **TMP** -Umgebungsvariablen angegebenen Verzeichnis bzw. im aktuellen Verzeichnis zu verwenden, wenn kein Verzeichnis angegeben ist.
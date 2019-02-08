---
title: Editierbare Dateitypen für Ressourcen (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: c40f9204-f2f2-400b-9f53-53b7bf291356
ms.openlocfilehash: 9f688c144a3453c2de849b36f34f6a465e3dfeae
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905718"
---
# <a name="editable-file-types-for-resources-c"></a>Editierbare Dateitypen für Ressourcen (C++)

Sie können die folgenden Dateitypen öffnen und die darin enthaltenen Ressourcen bearbeiten.

|Dateiname|Beschreibung|
|---------------|-----------------|
|.rc|Ressourcenskriptdateien|
|.rct|Ressourcenvorlagendateien|
|.res|Ressourcendateien|
|.resx|Verwaltete Ressourcendateien|
|.exe|Ausführbare Dateien.|
|.dll|Dynamic Link Library-Dateien.|
|.bmp, .ico, .dib und .cur|Bitmap-, Symbol-, Symbolleisten- und Cursordateien|

## <a name="files-affected-by-resource-editing"></a>Von der ressourcenbearbeitung betroffene Dateien

Die Visual Studio-Umgebung arbeitet während der Sitzung zur Bearbeitung von Ressourcen mit den in der folgenden Tabelle angegebenen Dateien.

|Dateiname|Beschreibung|
|---------------|-----------------|
|Resource.h|Durch die Entwicklungsumgebung generierte Headerdatei; enthält Symboldefinitionen. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|
|Filename.aps|Binäre Version der aktuellen Ressourcenskriptdatei; zum schnellen Laden verwendet.<br /><br /> .rc- oder resource.h-Dateien werden von Ressourcen-Editoren nicht direkt gelesen. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei nicht mehr mit der .rc-Datei synchron ist, wird die .rc-Datei neu generiert (z. B. überschreibt der Ressourcen-Editor beim Speichern die .rc-Datei und resource.h-Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md). (In der Regel sollten Sie nicht die .aps-Datei in der quellcodeverwaltung enthalten.)|
|.rc|Ressourcenskriptdatei, die Skript für die Ressourcen im aktuellen Projekt enthält. Diese Datei wird bei jedem Speichern durch die .aps-Datei überschrieben. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)
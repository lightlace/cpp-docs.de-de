---
title: Ressourcenbearbeitung betroffene Dateien | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource editing
- resources [Visual Studio], editing
ms.assetid: d0820df1-ba84-40ac-bce9-29ea5ee7e3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b165dca13e30e12e1a4fdc85056920b7c10ee586
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238655"
---
# <a name="files-affected-by-resource-editing"></a>Von der Ressourcenbearbeitung betroffene Dateien
Die Visual Studio-Umgebung arbeitet während der Sitzung zur Bearbeitung von Ressourcen mit den in der folgenden Tabelle angegebenen Dateien.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|Resource.h|Durch die Entwicklungsumgebung generierte Headerdatei; enthält Symboldefinitionen. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|  
|Filename.aps|Binäre Version der aktuellen Ressourcenskriptdatei; zum schnellen Laden verwendet.<br /><br /> .rc- oder resource.h-Dateien werden von Ressourcen-Editoren nicht direkt gelesen. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei nicht mehr mit der .rc-Datei synchron ist, wird die .rc-Datei neu generiert (z. B. überschreibt der Ressourcen-Editor beim Speichern die .rc-Datei und resource.h-Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Informationen zur Erhaltung von Kommentaren finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md). (In der Regel sollte nicht die .aps-Datei in der quellcodeverwaltung eingeschlossen werden.)|  
|.rc|Ressourcenskriptdatei, die Skript für die Ressourcen im aktuellen Projekt enthält. Diese Datei wird bei jedem Speichern durch die .aps-Datei überschrieben. (Enthalten Sie diese Datei in der quellcodeverwaltung.)|  
  

  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)
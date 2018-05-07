---
title: ATL-Programm oder Steuern von Quell- und Headerdateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8e5065cebab002e9c48aef560eb9f2feab67e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL-Programm oder Steuern von Quell- und Headerdateien
Die folgenden Dateien werden erstellt, wenn Sie abhängig von den Optionen, die Sie für das Projekt auswählen, die Sie erstellen ein ATL-Projekts in Visual Studio erstellen.  
  
 All diese Dateien befinden sich der *Projname* Verzeichnis, und im Ordner Headerdateien (.h-Dateien) oder der Ordner für Quelldateien (CPP-Dateien) im Projektmappen-Explorer.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|*Projektname*h|Die wichtigsten Include-Datei, die mit der C++-Schnittstellendefinitionen und GUID-Deklarationen in ATLSample.idl definierten Elemente. Er wird während der Kompilierung von MIDL erneut generiert.|  
|*Projektname*cpp|Die Quelldatei des Hauptprogramms gestartet. Es enthält die Implementierung der DLL Exporte für in-Process-Server und die Implementierung von `WinMain` für einen lokalen Server. Für einen Dienst implementiert dies außerdem alle Dienstverwaltungsfunktionen.|  
|Resource.h|Die Headerdatei für die Ressourcendatei.|  
|"Stdafx.cpp"|Enthält die Dateien "stdafx.h" und Atlimpl.cpp.|  
|"Stdafx.h"|Enthält die ATL-Headerdateien.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC-Programm oder Steuern von Quell- und Headerdateien](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR-Projekte](../ide/files-created-for-clr-projects.md)
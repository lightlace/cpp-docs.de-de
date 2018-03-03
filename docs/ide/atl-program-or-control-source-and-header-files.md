---
title: ATL-Programm oder Steuern von Quell- und Headerdateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
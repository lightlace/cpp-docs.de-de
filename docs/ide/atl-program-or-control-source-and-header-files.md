---
title: ATL-Programm oder Steuern von Quell- und Headerdateien | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33321625"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL-Programm oder Steuern von Quell- und Headerdateien
Folgende Dateien werden abhängig von den ausgewählten Optionen für das Projekt erstellt, wenn Sie ein ATL-Projekt in Visual Studio erstellen.  
  
 Diese Dateien befinden Sich alle im Verzeichnis *Projname*. Im Projektmappen-Explorer befinden diese sich entweder im Ordner „Headerdateien“ (H-Dateien) oder im Ordner „Quelldateien“ (CPP-Dateien).  
  
|Dateiname|description|  
|---------------|-----------------|  
|*Projname*.h|Die Hauptincludedatei, die die C++-Schnittstellendefinitionen und GUID-Deklarationen der in der Datei „ATLSample.idl“ definierten Elemente enthält. Sie wird während der Kompilierung von MIDL erneut generiert.|  
|*Projname*.cpp|Die Quelldatei des Hauptprogramms. Sie enthält die Implementierung der Exporte für einen In-Process-Server Ihrer DLL und die Implementierung von `WinMain` für einen lokalen Server. Für einen Dienst implementiert sie zusätzlich alle Dienstverwaltungsoptionen.|  
|Resource.h|Die Headerdatei für die Ressourcendatei|  
|StdAfx.cpp|Enthält die Dateien „StdAfx.h“ und „Atlimpl.cpp“.|  
|StdAfx.h|Enthält die ATL-Headerdateien.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC Program or Control Source and Header Files (ATL-Programm oder Steuern von Quell- und Headerdateien)](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR Projects (CLR-Projekte)](../ide/files-created-for-clr-projects.md)
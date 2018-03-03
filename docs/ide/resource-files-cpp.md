---
title: Ressourcendateien (C++) | Microsoft Docs
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
- resource files
- resources [C++]
- file types [C++], resource files
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 097ae6d1486292d7dcc62dd4191e16f57e6f0a3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-files-c"></a>Ressourcendateien (C++)
Ressourcen sind Benutzeroberflächenelemente, die Informationen für den Benutzer bereitstellen. Bitmaps, Symbole, Symbolleisten und Cursor sind alle Ressourcen auf. Einige Ressourcen können bearbeitet werden, um eine Aktion, z. B. in einem Menü auswählen oder Eingeben von Daten in das Dialogfeld Ausführen.  
  
 Finden Sie unter [arbeiten mit Ressourcen](../windows/working-with-resource-files.md) für Weitere Informationen.  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projektname*RC|*Projektname*|Quelldateien|Die Ressourcenskriptdatei für das Projekt. Die Ressourcenskriptdatei enthält die folgenden, je nach Art des Projekts, und die Unterstützung für das Projekt (z. B. Symbolleisten, Dialogfelder oder HTML) ausgewählt:<br /><br /> -Standard menüdefinition.<br />-Tabellen Accelerator und Zeichenfolge.<br />-Standard **zu** (Dialogfeld).<br />– Andere Dialogfelder.<br />– Die Symboldatei (Res\\*Projname*ICO).<br />-Versionsinformationen.<br />-Bitmaps.<br />-Symbolleiste.<br />-HTML Dateien.<br /><br /> Die Ressourcendatei enthält die Datei Afxres.rc für Microsoft Foundation Class-Standardressourcen.|  
|Resource.h|*Projektname*|Headerdateien|Die Ressource-Header-Datei, die Definitionen für die vom Projekt verwendeten Ressourcen enthält.|  
|*Projektname*RC2|*Projektname*\res|Quelldateien|Die Skriptdatei enthält zusätzliche Ressourcen, die vom Projekt verwendet. Sie können die RC2-Datei am Anfang des Projekts RC-Datei einschließen.<br /><br /> RC2-Dateien ist nützlich für das Einschließen von Ressourcen durch mehrere unterschiedliche Projekte verwendet. Anstatt die gleichen Ressourcen mehrere Male für verschiedene Projekte erstellen, können sie in einer RC2-Datei abgelegt werden und enthalten die RC2-Datei in die Datei RC-Hauptdatei abweicht.|  
|*Projektname*DEF|*Projektname*|Quelldateien|Die Moduldefinitionsdatei für eine DLL-Projekt. Für ein Steuerelement stellt er den Namen und die Beschreibung des Steuerelements sowie die Größe des Heaps zur Laufzeit bereit.|  
|*Projektname*ICO|*Projektname*\res|Ressourcendateien|Die Symboldatei für das Projekt oder das Steuerelement. Dieses Symbol wird angezeigt, wenn die Anwendung minimiert wird. Sie dient auch in der Anwendungsverzeichnis **zu** Feld. Standardmäßig MFC enthält das Symbol "MFC" und ATL stellt das Symbol "ATL".|  
|*Projektname*doc.ico vorhanden sind|*Projektname*\res|Ressourcendateien|Die Symboldatei für ein MFC-Projekt, das Unterstützung für die Dokument-/Ansichtarchitektur umfasst.|  
|ToolBar.bmp|*Projektname*\res|Ressourcendateien|Die Bitmapdatei, die die Anwendung bzw. eines Steuerelements in einer Symbolleiste oder Palette darstellt. Diese Bitmap ist in der Ressourcendatei des Projekts enthalten. Die erste Symbolleiste und Statusleiste werden erstellt, der **CMainFrame** Klasse.|  
|Ribbon.mfcribbon ms|*Projektname*\res|Ressourcendateien|Die Ressourcendatei mit dem XML-Code, der die Schaltflächen, Steuerelemente und Attribute im Menüband definiert. Weitere Informationen finden Sie unter [Ribbon Designer (MFC)](../mfc/ribbon-designer-mfc.md).|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)
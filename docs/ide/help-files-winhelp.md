---
title: Hilfedateien (WinHelp) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a5036aa329c0b4004bd7ada724c62e1a1669f050
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="help-files-winhelp"></a>Hilfedateien (WinHelp)
Die folgenden Dateien werden erstellt, wenn Sie die WinHelp-Typ der Hilfe und Unterstützung für Ihre Anwendung, indem Sie die Auswahl hinzufügen der **kontextbezogene Hilfe** Kontrollkästchen auswählen und dann **WinHelp-Format** in der [Erweiterte Funktionen](../mfc/reference/advanced-features-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung.  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projektname*HPJ|*Projektname*\hlp|Quelldateien|Die Hilfeprojektdatei, die vom Hilfecompiler zum Erstellen von Ihrer Anwendung oder die Hilfedatei des Steuerelements verwendet wird.|  
|*Projektname*RTF|*Projektname*\hlp|Hilfedateien|Enthält Informationen zum Anpassen der HPJ-Datei und Vorlage Themen, die Sie bearbeiten können.|  
|*Projektname*CNT|*Projektname*\hlp|Hilfedateien|Stellt die Struktur für die **Inhalt** Fenster in der Windows-Hilfe.|  
|MakeHelp.bat|*Projektname*|Quelldateien|Vom System verwendet, um das Help-Projekt zu erstellen, wenn das Projekt kompiliert wird.|  
|Print.RTF|*Projektname*\hlp|Hilfedateien|Erstellt, wenn Ihr Projekt druckunterstützung (Standard) umfasst. Beschreibt die Druckbefehle und Dialogfelder.|  
|*.bmp|*Projektname*\hlp|Ressourcendateien|Enthalten Sie Bilder für die verschiedenen generierten Datei Hilfethemen.|  
  
 Sie können die WinHelp-Unterstützung zu einem MFC-ActiveX-Steuerelement-Projekt hinzufügen, durch Auswahl **Hilfedateien generieren** in der [Anwendungseinstellungen](../mfc/reference/application-settings-mfc-activex-control-wizard.md) MFC-ActiveX-Steuerelement-Assistenten auf der Registerkarte. Die folgenden Dateien werden dem Projekt hinzugefügt, wenn Sie Hilfe und Unterstützung auf MFC-ActiveX-Steuerelement hinzufügen:  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projektname*HPJ|*Projektname*\hlp|Quelldateien|Die Projektdatei, die vom Hilfecompiler zum Erstellen von Ihrer Anwendung oder die Hilfedatei des Steuerelements verwendet wird.|  
|*Projektname*RTF|*Projektname*\hlp|Projekt|Enthält Informationen zum Anpassen der HPJ-Datei und Vorlage Themen, die Sie bearbeiten können.|  
|MakeHelp.bat|*Projektname*|Quelldateien|Vom System verwendet, um das Help-Projekt zu erstellen, wenn das Projekt kompiliert wird.|  
|Bullet.bmp|*Projektname*|Ressourcendateien|Von standard-Hilfethemen verwendet, um Aufzählung darzustellen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)
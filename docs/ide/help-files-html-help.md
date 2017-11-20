---
title: Hilfedateien (HTML-Hilfe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b97c73514d534ba6092c8b1c3ec5cfa676500538
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="help-files-html-help"></a>Hilfedateien (HTML-Hilfe)
Die folgenden Dateien werden erstellt, wenn Sie die HTML-Hilfe Hilfe und Unterstützung für die Anwendung dazu hinzufügen der **kontextbezogene Hilfe** Kontrollkästchen auswählen und dann **HTML-Hilfe-Format** in der [Erweiterte Funktionen](../mfc/reference/advanced-features-mfc-application-wizard.md) Seite des Assistenten für die MFC-Anwendung.  
  
|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projektname*hhp|*Projektname*\hlp|HTML-Hilfedateien|Die Hilfe-Projektdatei. Es enthält die Daten, die erforderlich sind, um die Hilfedateien in ein HxS-Datei oder eine CHM-Datei zu kompilieren.|  
|*Projektname*.hhk|*Projektname*\hlp|HTML-Hilfedateien|Enthält einen Index der Hilfethemen.|  
|*Projektname*.hhc|*Projektname*\hlp|HTML-Hilfedateien|Der Inhalt des Hilfeprojekts.|  
|Makehtmlhelp.bat|*Projektname*|Quelldateien|Vom System verwendet, um das Help-Projekt zu erstellen, wenn das Projekt kompiliert wird.|  
|Afxcore.htm|*Projektname*\hlp|HTML-Hilfethemen|Enthält die Standardhilfethemen für MFC-Standardbefehle und Bildschirmobjekte. Fügen Sie dieser Datei eigene Hilfethemen hinzu.|  
|Afxprint.htm|*Projektname*\hlp|HTML-Hilfethemen|Enthält die Hilfethemen für die Druckbefehle.|  
|*.jpg; \*GIF|*Projektname*\hlp\Images|Ressourcendateien|Enthalten Sie Bilder für die verschiedenen generierten Datei Hilfethemen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)
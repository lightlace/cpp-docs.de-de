---
title: Hilfedateien (HTML-Hilfe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04d3171f1bba6b803c68b7a3b753cc70825671bb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383544"
---
# <a name="help-files-html-help"></a>Hilfedateien (HTML-Hilfe)

Die folgenden Dateien werden erstellt, wenn Sie den HTML-Hilfstyp der Hilfsunterstützung Ihrer Anwendung hinzufügen, indem Sie das Kontrollkästchen **Kontextbezogene Hilfe** aktivieren und das **HTML-Hilfeformat** auf der Seite [Erweiterte Funktionen](../mfc/reference/advanced-features-mfc-application-wizard.md) des MFC-Anwendungs-Assistenten auswählen.

|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung |
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hhp|*Projname*\hlp|HTML-Hilfedateien|Die Hilfsprojektdatei. Sie enthält die Daten, die zum Kompilieren der Hilfedateien in eine HXS- oder CHM-Datei erforderlich sind.|
|*Projname*.hhk|*Projname*\hlp|HTML-Hilfedateien|Enthält einen Index der Hilfethemen.|
|*Projname*.hhc|*Projname*\hlp|HTML-Hilfedateien|Der Inhalt des Hilfeprojekts.|
|Makehtmlhelp.bat|*Projname*|Quelldateien|Wird vom System zum Erstellen des Hilfeprojekts verwendet, wenn das Projekt kompiliert wird.|
|Afxcore.htm|*Projname*\hlp|HTML-Hilfethemen|Enthält die Standardhilfethemen für standardmäßige MFC-Befehle und Bildschirmobjekte. Dieser Datei können Sie Ihre eigenen Hilfethemen hinzufügen.|
|Afxprint.htm|*Projname*\hlp|HTML-Hilfethemen|Enthält Hilfethemen für die Druckbefehle.|
|*.jpg; \*.gif|*Projname*\hlp\Images|Ressourcendateien|Enthält Bilder zu den verschiedenen generierten Hilfedateithemen.|

## <a name="see-also"></a>Siehe auch

[Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)
---
title: Hilfedateien (WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 6810b3f608b9fa7892b686d72056994fb98c92db
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707467"
---
# <a name="help-files-winhelp"></a>Hilfedateien (WinHelp)

Die folgenden Dateien werden erstellt, wenn Sie den WinHelp-Typ der Hilfsunterstützung Ihrer Anwendung hinzufügen, indem Sie das Kontrollkästchen **Kontextbezogene Hilfe** aktivieren und das **WinHelp-Format** auf der Seite [Erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) des MFC-Anwendungs-Assistenten auswählen.

|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|Quelldateien|Die Hilfeprojektdatei, die vom Hilfecompiler verwendet wird, um Ihr Programm oder die Hilfedatei des Steuerelements zu erstellen.|
|*Projname*.rtf|*Projname*\hlp|Hilfedateien|Enthält Themenvorlagen, die Sie bearbeiten können, und Informationen zum Anpassen Ihrer HPJ-Datei.|
|*Projname*.cnt|*Projname*\hlp|Hilfedateien|Stellt die Struktur für das Fenster **Inhalt** in der Windows-Hilfe bereit.|
|Makehelp.bat|*Projname*|Quelldateien|Wird vom System zum Erstellen des Hilfeprojekts verwendet, wenn das Projekt kompiliert wird.|
|Print.rtf|*Projname*\hlp|Hilfedateien|Wird erstellt, wenn Ihr Projekt Druckunterstützung enthält (Standard). Beschreibt die Druckbefehle und Dialogfelder.|
|*.bmp|*Projname*\hlp|Ressourcendateien|Enthält Bilder zu den verschiedenen generierten Hilfedateithemen.|

Sie können einem MFC-ActiveX-Steuerelement-Projekt die WinHelp-Unterstützung hinzufügen, indem Sie in der Registerkarte [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) des MFC-ActiveX-Steuerelement-Assistenten auf **Hilfedateien generieren** klicken. Die folgenden Dateien werden Ihrem Projekt hinzugefügt, wenn Sie einem MFC-ActiveX-Steuerelement die Hilfsunterstützung hinzufügen:

|Dateiname|Speicherort für das Verzeichnis|Speicherort für den Projektmappen-Explorer|Beschreibung|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|Quelldateien|Die Projektdatei, die vom Hilfecompiler verwendet wird, um Ihr Programm oder die Hilfedatei des Steuerelements zu erstellen.|
|*Projname*.rtf|*Projname*\hlp|Projekt|Enthält Themenvorlagen, die Sie bearbeiten können, und Informationen zum Anpassen Ihrer HPJ-Datei.|
|Makehelp.bat|*Projname*|Quelldateien|Wird vom System zum Erstellen des Hilfeprojekts verwendet, wenn das Projekt kompiliert wird.|
|Bullet.bmp|*Projname*|Ressourcendateien|Wird bei Standardhilfethemen zum Anzeigen von Aufzählungen verwendet.|

## <a name="see-also"></a>Siehe auch

[Für Visual Studio C++-Projekte erstellte Dateitypen](file-types-created-for-visual-cpp-projects.md)

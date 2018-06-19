---
title: Assistenten und die Ressourcen-Editoren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33fb1caa496c34111de133a113433a614ff5eb22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383835"
---
# <a name="wizards-and-the-resource-editors"></a>Assistenten und der Ressourcen-Editor
Visual C++ enthält mehrere Assistenten für die Verwendung in MFC-Programmierung, zusammen mit vielen integrierten Ressourcen-Editoren. Für ActiveX-Programmierung, Steuerelemente der [ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md) dient dem Zweck, ähnlich der MFC-Anwendung-Assistenten. Während Sie die MFC-Anwendungen ohne die meisten dieser Tools schreiben können, wird die Tools erheblich vereinfachen und beschleunigen Ihre Arbeit.  
  
##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> Verwenden Sie die MFC-Anwendung-Assistent zum Erstellen einer Mfc_anwendung  
 Verwenden der [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md) ein MFC-Projekt in Visual C++ erstellen, die OLE umfassen und die Unterstützung der Datenbank. Dateien im Projekt enthalten, die Anwendung, Dokument anzeigen und Rahmenfensterklassen; Standardressourcen, einschließlich Menüs und eine optionale Symbolleiste; andere erforderliche Windows-Dateien; und optionale .rtf-Dateien enthält, standardmäßige Windows-Hilfethemen, die Sie ändern können und ergänzen, die Hilfedatei des Programms erstellen.  
  
##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Verwenden Sie zum Verwalten von Klassen und Windows-Meldungen Klassenansicht  
 Klasse Ansicht hilft Handlerfunktionen für die Windows-Meldungen und Befehle erstellen, erstellen und Verwalten von Klassen, Klassenmember Variablen erstellen, Erstellen von Automation-Methoden und Eigenschaften, Datenbankklassen und vieles mehr erstellen.  
  
> [!NOTE]
>  Klassenansicht können Sie virtuelle Funktionen in den MFC-Klassen überschreiben. Wählen Sie die Klasse und die virtuelle Funktion, die außer Kraft setzen. Die restliche Prozess ähnelt Meldungsbehandlung, wie in den folgenden Abschnitten beschrieben.  
  
 Anwendungen, die unter Windows ausgeführt werden [Nachricht driven](../mfc/message-handling-and-mapping.md). Dazu führen, dass Windows zum Senden von Nachrichten auf dem Windows im Programm Benutzeraktionen und andere Ereignisse, die in der ausgeführten Anwendung auftreten. Beispielsweise, wenn der Benutzer die Maus in einem Fenster klickt, sendet Windows eine `WM_LBUTTONDOWN` Nachricht, wenn die linke Maustaste gedrückt wird und ein `WM_LBUTTONUP` Meldung, wenn die Maustaste losgelassen wird. Außerdem sendet Windows **WM_COMMAND** Nachrichten, wenn der Benutzer über die Menüleiste Befehle auswählt.  
  
 In der MFC-Framework können verschiedene Objekte, z. B. Dokumente, Ansichten, Rahmenfenster, Dokumentvorlagen und das Anwendungsobjekt "Nachrichten verarbeiten". Ein solches Objekt "Handlerfunktion" als eines seiner Member stellt Funktionen bereit, und das Framework wird die eingehende Nachricht der Handler zugeordnet.  
  
 Ein großer Teil der Ihre Aufgabe als Programmierer ist welche Nachrichten zuordnen, welche Objekte auswählen und implementieren Sie dann diese Zuordnung. Zu diesem Zweck verwenden Sie Klassenansicht und im Eigenschaftenfenster angezeigt.  
  
 Eigenschaftenfenster erstellt leere Meldungshandler-Memberfunktionen, und der Quellcode-Editors verwendet, um den Text des ereignishandlers zu implementieren. Sie können auch erstellen oder bearbeiten (einschließlich Ihrer Wahl, nicht von MFC-Klassen abgeleitete Klassen) Klassen und ihre Member mit Klassenansicht. Weitere Informationen zur Verwendung der Klassenansicht und Assistenten, mit denen Code zu einem Projekt hinzufügen, finden Sie unter [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md).  
  
##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Verwenden Sie die Ressourcen-Editoren zum Erstellen und Bearbeiten von Ressourcen  
 Verwenden Sie die Visual C++ [Ressourcen-Editoren](../windows/resource-editors.md) erstellen und Bearbeiten von Menüs, Dialogfeldern, benutzerdefinierte Steuerelemente, Zugriffstasten, Bitmaps, Symbole, Cursor, Zeichenfolgen und Versionsressourcen. Ab Visual C++, Version 4.0 wird als ein Symbolleisten-Editor Erstellen von Symbolleisten wesentlich einfacher.  
  
 Um Sie noch mehr zu erleichtern, bietet die Microsoft Foundation Class-Bibliothek eine Datei mit allgemeinen. RES, die "ClipArt" Ressourcen enthält, die Sie von COMMON kopieren können. RES und Einfügen in eine eigene Ressourcendatei. ALLGEMEINE. RES enthält Symbolleisten-Schaltflächen, allgemeine Cursor, Symbole und mehr. Sie können verwenden, ändern und verteilen diese Ressourcen in Ihrer Anwendung. Weitere Informationen zu allgemeinen. RES, finden Sie unter der [Clipart-Beispiel](../visual-cpp-samples.md).  
  
 MFC-Anwendung-Assistenten, die Visual C++-Assistenten Ressourcen-Editoren und MFC-Framework viel Arbeit für Sie erledigen, und stellen Ihren Code leichter verwalten. Der Großteil der anwendungsspezifischen Code befindet sich in Ihrem Dokument und Ansicht-Klassen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)

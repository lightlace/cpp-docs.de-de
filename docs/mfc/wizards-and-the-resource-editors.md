---
title: "Assistenten und der Ressourcen-Editor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], und MFC"
  - "Klassenansicht (Tool), Verwalten von Windows-Meldungen"
  - "Editoren, Ressource"
  - "MFC [C++], Ressourcen-Editoren"
  - "MFC [C++], Assistenten"
  - "MFC-Anwendungs-Assistent"
  - "Ressourcen-Editoren, MFC"
  - "Assistenten [C++], MFC-Programmierung"
  - "Assistenten [MFC]"
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Assistenten und der Ressourcen-Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ enthält einigen Assistenten zur Verwendung in MFC\-Programmierung, zusammen mit vielen integrierten Ressourcen\-Editoren ein.  Für programmierende ActiveX\-Steuerelemente, dient [ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md) einen Zweck ähnlich dem des MFC\-Anwendungs\-Assistenten.  Während Sie MFC\-Anwendungen ohne die meisten dieser Tools schreiben können, die Tools vereinfachen und erheblich beschleunigen die Arbeit.  
  
##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> Verwenden Sie den MFC\-Anwendungs\-Assistenten, eine MFC\-Anwendung zu erstellen  
 Verwenden Sie [MFC\-Anwendungs\-Assistent](../mfc/reference/mfc-application-wizard.md), um ein MFC\-Projekt in Visual C\+\+ erstellen, die OLE und Datenbankunterstützung einschließen kann.  Dateien im Projekt enthalten die Anwendung, dokumentieren, zeigen und Rahmenfensterklassen an; Standardressourcen, einschließlich Menüs und eine optionale Symbolleiste; andere erforderliche Windows\-Dateien; und optionales .rtf Dateien das Einbinden von Standard\-Windows\-Hilfethemen, die Sie überarbeiten und erweitern können, um Hilfedatei des Programms zu erstellen.  
  
##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Verwendungs\-Klassenansicht, um Klassen von Windows\-Meldungen von und zu verwalten  
 Erstellen Sie Klassenansichtshilfen Handlerfunktionen für Windows\-Meldungen und Befehle, erstellen und verwalten, erstellen Klassen Klassenmembervariablen, erstellen Automatisierungsmethoden und Eigenschaften, erstellen Datenbankklassen und mehr.  
  
> [!NOTE]
>  Der Klassenansicht ist auch hilfreich, z virtueller Funktionen in MFC\-Klassen zu überschreiben.  Wählen Sie die Klasse und die virtuelle Funktion aus, um zu überschreiben.  Der Rest des Prozesses ist die Meldungsbehandlung ähnlich, wie in den folgenden Abschnitten beschrieben.  
  
 Anwendungen, die unter Windows ausgeführt, sind [Meldung gesteuert](../mfc/message-handling-and-mapping.md).  Benutzeraktionen und andere Ereignisse, die in der ausgeführten Programmursache Windows auftreten, um Nachrichten zu Fenstern im Programm zu senden.  Wenn der Benutzer mit der Maus in einem Fenster klickt, Windows `WM_LBUTTONDOWN` sendet eine Meldung, wenn die linke Maustaste und eine Meldung `WM_LBUTTONUP` gedrückt wird, wenn die Schaltfläche freigegeben wird.  Windows wird außerdem **WM\_COMMAND** Meldungen, wenn der Benutzer Befehle in der Menüleiste auswählt.  
  
 Im MFC\-Framework können verschiedene Objekte, wie Dokumente, Ansichten, Rahmenfenster, Dokumentvorlagen und das Anwendungsobjekt, Meldungen "bearbeiten".  Ein solches Objekt stellt eine Handlerfunktion "" als eine der Memberfunktionen bereit, und das Framework ordnet der eingehenden Meldungen zu seinem Handler an.  
  
 Ein großer Teil der Programmieraufgabe wählt aus, der mit welchen Objekten und diese Zuordnung dann zu implementieren zuzuordnen die Meldungen.  Dazu verwenden Sie die Klassenansicht, und das Eigenschaftenfenster.  
  
 Das Eigenschaftenfenster wird leere Meldungshandlermemberfunktionen, und Sie verwenden den Quellcode\-Editor, um den Text des Handlers zu implementieren.  Sie können Klassen \(einschließlich Klassen von eigenen, nicht von MFC\-Klassen abgeleitet\) und ihre Member mit Klassenansicht auch erstellen oder bearbeiten.  Weitere Informationen über die Verwendung der Klassenansicht und über Assistenten, die einem Projekt Code hinzufügen können, finden Sie unter [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md).  
  
##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Verwenden Sie den Ressourcen\-Editoren, um Ressourcen zu erstellen und zu bearbeiten  
 Verwenden Sie [Ressourcen\-Editoren](../mfc/resource-editors.md) von Visual C\+\+, um Menüs, Dialogfeldern, benutzerdefinierte Steuerelemente, Zugriffstasten, Bitmaps, Symbole, Cursor, Zeichenfolgen und Freigeben der verwendeten Ressourcen zu erstellen und zu bearbeiten.  Ab Visual C\+\+\-Version 4.0, macht ein Symbolleisten\-Editor, Symbolleisten Erstellen einfacher.  
  
 Um Sie sogar zu erleichtern, stellt die Microsoft Foundation Class\-Bibliothek eine Datei mit dem Namen COMMON.RES, die "ClipArt\-" Ressourcen enthält die Sie von COMMON.RES und in eigene Ressourcendatei kopieren können.  COMMON.RES schließt Symbolleistenschaltflächen, allgemeine Cursor, Symbole und mehr ein.  Sie können diese Ressourcen in der Anwendung verwenden, ändern und verteilen.  Weitere Informationen über COMMON.RES, finden Sie unter [ClipArt\-Beispiel](../top/visual-cpp-samples.md).  
  
 Der MFC\-Anwendungs\-Assistent, die Visual C\+\+\-Assistenten, die Verwendung und das MFC\-Framework übernehmen deutlich Arbeit für Sie und ausführen, den Code Verwalten viel einfacher.  Die Sammelverarbeitung anwendungsspezifischen des Codes sind im Dokument in und Ansichtsklassen.  
  
## Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
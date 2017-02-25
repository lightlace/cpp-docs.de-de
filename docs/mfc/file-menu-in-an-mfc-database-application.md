---
title: "Das Dateimen&#252; in einer MFC-Datenbankanwendung | Microsoft Docs"
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
  - "Datei (Menü)"
  - "Datenbankanwendungen [C++] Befehle im Menü „Datei“"
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Das Dateimen&#252; in einer MFC-Datenbankanwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einer MFC\-Datenbankanwendung erstellen und nicht wie die Serialisierung verwenden, sollten Sie das geöffnete, den Abschluss, den Speicherungs\- und den Speicherungs\- als Befehle im Menü Datei interpretieren?  Während es keine Formatrichtlinien für diese Frage gibt, sind hier einige Vorschläge:  
  
-   Schließen Sie den Befehl der geöffneten Menü vollständig.  
  
-   Interpretieren Sie den geöffneten Befehl als "geöffnete Datenbank" und zeigen Sie dem Benutzer eine Liste der Datenquellen an, die von der Anwendung erkannt wird.  
  
-   Interpretieren Sie den geöffneten Befehl, z möglicherweise "öffnen Sie Profil." Behalten Sie öffnen zum Öffnen einer serialisierten Datei, jedoch Datei verwendet, um ein serialisiertes Dokument zu speichern, das "Benutzerprofil" Informationen, wie die Einstellungen des Benutzers, einschließlich seiner oder Anmelde\-ID enthält \(optional ausschließlich des Kennworts und die Datenquelle, er oder sie funktioniert zuletzt mit.  
  
 Der MFC\-Anwendungs\-Assistent unterstützt das Erstellen einer Anwendung ohne der Menü Datei\-Befehle.  Wählen Sie die Option **Datenbankansicht ohne Dateiunterstützung** auf der Seite **Datenbankunterstützung** aus.  
  
 Um ein Menü Befehl auf eine besondere Weise interpretieren, müssen Sie mindestens Befehlshandler, meist im `CWinApp` überschreiben abgeleiteten Klasse.  Wenn Sie vollständig `OnFileOpen` \(das `ID_FILE_OPEN` den Befehl implementiert\) überschreiben, um "geöffnete Datenbank einzubeziehen: "  
  
-   Rufen Sie die Basisklassenversion von `OnFileOpen` auf, da Sie vollständig die Standardimplementierung des Framework des Befehls ersetzen.  
  
-   Verwenden Sie stattdessen den Handler, um Datenquellen Dialogfeldlisten anzuzeigen.  Sie können ein solches Dialogfeld anzeigen, indem Sie `CDatabase::OpenEx` oder `CDatabase::Open` mit dem Parameter **NULL** aufrufen.  Damit wird ein ODBC\-Dialogfeld, das alle verfügbaren Datenquellen auf dem Computer des Benutzers angezeigt.  
  
-   Da Datenbankanwendungen in der Regel kein ganzes Dokument speichern, möchten Sie wahrscheinlich den Speicherungs\- entfernen und als Implementierungen speichern, außer, Sie verwenden ein serialisiertes Dokument verwenden, um die Profilinformationen zu speichern.  Andernfalls haben Sie möglicherweise den Befehl Speichern wie beispielsweise "Committransaktion." Weitere Informationen finden Sie im [Technischer Hinweis 22](../mfc/tn022-standard-commands-implementation.md) zum Überschreiben dieser Befehle.  
  
## Siehe auch  
 [Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md)
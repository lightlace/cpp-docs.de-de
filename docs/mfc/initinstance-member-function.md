---
title: "InitInstance-Memberfunktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [MFC], Initialisieren"
  - "Initialisieren von MFC-Anwendungen"
  - "InitInstance-Methode"
  - "MFC [C++], Initialisieren"
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# InitInstance-Memberfunktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Windows\-Betriebssystem ermöglicht Ihnen, um mehr als eine Kopie "," oder Instanz derselben Anwendung auszuführen.  `WinMain` ruft [InitInstance](../Topic/CWinApp::InitInstance.md) jedes Mal eine neue Instanz der Anwendung auf.  
  
 Die standardmäßige `InitInstance` Implementierung, mit dem MFC\-Anwendungs\-Assistenten erstellt wird, werden die folgenden Aufgaben aus:  
  
-   Als zentrale Aktion erstellt die Dokumentvorlagen, die wiederum Dokumente, Ansichten und Rahmenfenster erstellen.  Eine Beschreibung dieses Prozesses, finden Sie unter [Dokumentvorlagen\-Erstellung](../mfc/document-template-creation.md).  
  
-   Laststandarddateioptionen einer INI\-Datei oder der Windows\-Registrierung, einschließlich der Namen der zuletzt verwendeten Dateien.  
  
-   Registriert mindestens Dokumentvorlagen.  
  
-   Für eine MDI\-Anwendung stellt ein Hauptrahmenfenster erstellt.  
  
-   Verarbeitet die Befehlszeile, um ein Dokument zu öffnen, das in der Befehlszeile oder ein neues, leeres Dokument zu öffnen angegeben wird.  
  
 Sie können eigenen Initialisierungscode hinzufügen oder den Code ändern, der vom Assistenten geschrieben wird.  
  
> [!NOTE]
>  MFC\-Anwendungen müssen als Singlethread\-Apartment \(STA\) initialisiert werden.  Wenn Sie [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) in der `InitInstance` Überschreibung aufrufen, geben Sie `COINIT_APARTMENTTHREADED` an \(statt `COINIT_MULTITHREADED`\).  Weitere Informationen finden Sie unter "PRB: MFC\-Anwendung reagiert nicht mehr, wenn Sie die Anwendung als Multithread\-Apartment initialisieren \(828643\)" unter [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;828643](http://support.microsoft.com/default.aspx?scid=kb;en-us;828643).  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)
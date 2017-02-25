---
title: "MAPI-Unterst&#252;tzung in MFC | Microsoft Docs"
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
  - "CDocument-Klasse, und MAPI"
  - "MAPI-Unterstützung in MFC"
  - "MAPI, MFC"
  - "MFC, MAPI-Unterstützung"
  - "OnFileSendMail-Methode"
  - "OnUpdateFileSendMail-Methode"
ms.assetid: cafbecb1-0427-4077-b4b8-159bae5b49b8
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MAPI-Unterst&#252;tzung in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC\-Zubehörunterstützung für eine Teilmenge der Microsoft\-Messaging\-Anwendungsprogrammierschnittstelle \(MAPI\) in der **CDocument**\-Klasse.  Insbesondere hat **CDocument**\-Memberfunktionen, die bestimmen, ob E\-Mail\-Unterstützung auf dem Computer des Endbenutzers vorhanden ist und wenn ja, einen sendens\-E\-Mail\-Befehl aktiviert, dessen Standardbefehls\-id **ID\_FILE\_SEND\_MAIL** ist.  Die MFC\-Handlerfunktion für diesen Befehl ermöglicht dem Benutzer, ein Dokument über E\-Mail senden.  
  
> [!TIP]
>  Obwohl MFC nicht den gesamten MAPI\-Funktionssatz kapselt, können Sie MAPI\-Funktionen, als Sie noch direkt aufrufen können Win32\-API\-Funktionen direkt von MFC\-Programmen aufrufen.  
  
 Die sendens\-E\-Mail\-Befehl in der Anwendung bereitzustellen ist sehr einfach.  MFC stellt die Implementierung, um ein Dokument \(d, **CDocument** abgeleiteten Objekt\) als Anlage zu verpacken und als E\-Mail senden.  Diese Installation ist einem Datei\-Abwehrbefehl äquivalent, der den Inhalt des Dokuments der E\-Mail speichert \(serialisiert\).  Diese Implementierung benötigt den E\-Mail\-Client auf dem Computer des Benutzers auf, um dem Benutzer die Möglichkeit zu geben, die E\-Mails zu behandeln und Betreff\- und Meldungstext E\-Mail hinzuzufügen.  Benutzer finden die Benutzeroberfläche der vertrauten E\-Mail\-Anwendung.  Diese Funktionalität wird von zwei Memberfunktionen **CDocument** angegeben: `OnFileSendMail` und `OnUpdateFileSendMail`.  
  
 MAPI muss die Datei lesen, um die Anlage zu senden.  Wenn die Anwendung die Datendatei geöffnet während eines Funktionsaufrufs `OnFileSendMail` übergibt, muss die Datei mit einem Freigabenmodus geöffnet sein, der mehrere Prozessen ermöglicht, auf die Datei zuzugreifen.  
  
> [!NOTE]
>  Eine überschreibende Version von `OnFileSendMail` für `COleDocument` ordnungsgemäß Verbunddokumente Klasse bearbeitet.  
  
#### Um eine sendens\-E\-Mail implementieren Sie einen EXE\-Befehl mit MFC  
  
1.  Verwenden Sie den Visual C\+\+\-Menü\-Editor, um ein Menüelement hinzu, dessen Befehls\-ID **ID\_FILE\_SEND\_MAIL** ist.  
  
     Diese Befehls\-ID wird vom Framework in AFXRES.H. bereitgestellt.  Der Befehl kann an jedes Menü hinzugefügt werden, sondern nur **Datei** normalerweise dem Menü hinzugefügt.  
  
2.  Fügen Sie manuell Folgendes der Meldungszuordnung des Dokuments hinzu:  
  
     [!CODE [NVC_MFCDocView#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#9)]  
  
    > [!NOTE]
    >  Diese Meldungszuordnung funktioniert für ein Dokument, das entweder von **CDocument** oder von **COleDocument** abgeleitet ist \- sie hebt die richtige Basisklasse in beiden Fällen auf, obwohl die Meldungszuordnung in der abgeleiteten Dokumentklasse ist.  
  
3.  Erstellen Sie die Anwendung.  
  
 Wenn E\-Mail\-Unterstützung verfügbar ist, können MFC das Menüelement mit `OnUpdateFileSendMail` und verarbeitet anschließend den Befehl mit `OnFileSendMail`.  Wenn E\-Mail\-Unterstützung nicht verfügbar ist, entfernt MFC automatisch das Menüelement, damit der Benutzer davon.  
  
> [!TIP]
>  Anstatt Meldungszuordnungseinträgen, manuell hinzufügen, wie bereits beschrieben, können Sie das Eigenschaftenfenster Klasse verwenden, um Nachrichten auf Funktionen zuordnen.  Weitere Informationen finden Sie unter [Zuordnung von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Weitere Informationen finden Sie in der Übersicht [MAPI](../mfc/mapi.md).  
  
 Weitere Informationen zur **CDocument**\-Memberfunktionen, die MAPI aktivieren, finden Sie unter:  
  
-   [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)  
  
-   [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)  
  
-   [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)  
  
## Siehe auch  
 [MAPI](../mfc/mapi.md)
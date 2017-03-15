---
title: "Hinzuf&#252;gen mehrerer Ansichten zu einem Dokument | Microsoft Docs"
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
  - "Dokumente, Mehrere Ansichten"
  - "Mehrere Ansichten, SDI-Anwendungen"
  - "Einzeldokumentoberfläche (SDI), Hinzufügen von Ansichten"
  - "Ansichten, SDI-Anwendungen"
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Hinzuf&#252;gen mehrerer Ansichten zu einem Dokument
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In einer Single Document Interface \(SDI\)\- Anwendung, die mit der MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) erstellt wird, wird jeder Dokumenttyp mit einem einzelnen Ansichtstypen verwenden zugeordnet.  In einigen Fällen ist es empfehlenswert, die Möglichkeit haben, die aktuelle Ansicht eines Dokuments mit einer neuen Ansicht zu wechseln.  
  
> [!TIP]
>  Weitere Verfahren zum Implementieren mehrerer Ansichten für einen einzelnen Dokument, finden Sie unter [CDocument::AddView](../Topic/CDocument::AddView.md) und im Beispiel [COLLECT Sie](../top/visual-cpp-samples.md) MFC.  
  
 Diese Funktionalität können Sie implementieren, indem Sie neue `CView` abgeleitete Klasse und Code für die Ansichten zu einer bereits vorhandenen MFC\-Anwendung dynamisch wechseln hinzufügen.  
  
 Folgende Schritte werden ausgeführt:  
  
-   [Ändern Sie die vorhandene Anwendungsklasse](#vcconmodifyexistingapplicationa1)  
  
-   [Erstellen und Ändern Sie die Ansichtsklasse neue](#vcconnewviewclassa2)  
  
-   [Erstellen und fügen Sie die neue Ansicht an](#vcconattachnewviewa3)  
  
-   [Implementieren Sie die Vermittlungsaufgabe](#vcconswitchingfunctiona4)  
  
-   [Fügen Sie Unterstützung zum Umschalten der Ansicht hinzu](#vcconswitchingtheviewa5)  
  
 Der Rest dieses Themas gelangen Folgendes an:  
  
-   Der Name `CWinApp` abgeleitetes Objekt ist `CMyWinApp`, und `CMyWinApp` ist in MYWINAPP.H und in MYWINAPP.CPP deklariert und definiert.  
  
-   `CNewView` ist der Name neuen `CView` abgeleitetes Objekt und `CNewView` ist in NEWVIEW.H und in NEWVIEW.CPP deklariert und definiert.  
  
##  <a name="vcconmodifyexistingapplicationa1"></a> Ändern Sie die vorhandene Anwendungsklasse  
 Damit die Anwendung wechselt zwischen Ansichten, müssen Sie die Anwendungsklasse ändern, indem Sie Membervariablen hinzu, um die Ansichten und einer Methode zu speichern, um sie zu wechseln.  
  
 Fügen Sie folgenden Code in die Deklaration von `CMyWinApp` in MYWINAPP.H hinzu:  
  
 [!CODE [NVC_MFCDocViewSDI#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#1)]  
  
 Die neue Membervariablen, `m_pOldView` und `m_pNewView`, zeigen Sie die aktuelle Ansicht und das neu erstellte.  Die neue Methode \(`SwitchView`\) wird die Ansichten um, wenn es vom Benutzer angefordert wird.  Der Methodentext wird weiter unten in diesem Thema in [Implementieren Sie die Vermittlungsaufgabe](#vcconswitchingfunctiona4) erläutert.  
  
 Die letzte Änderung der Anwendungsklasse erfordert einschließlich einer neuen Headerdatei, die eine Windows\-Meldung \(**WM\_INITIALUPDATE**\) definiert die in der Vermittlungsaufgabe verwendet wird.  
  
 Fügen Sie die folgende Zeile im Einschließungsabschnitt von MYWINAPP.CPP ein:  
  
 [!CODE [NVC_MFCDocViewSDI#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#2)]  
  
 Speichern Sie die Änderungen und fahren Sie mit dem nächsten Schritt fort.  
  
##  <a name="vcconnewviewclassa2"></a> Erstellen und Ändern Sie die Ansichtsklasse neue  
 Das Erstellen der neuen Ansichtsklasse wird einfach gemacht, indem **Neue Klasse** den Befehl verwendet, der von der Klassenansicht verfügbar ist.  Die einzige Anforderung für diese Klasse besteht darin, dass sie von `CView` abgeleitet.  Fügen Sie die neue Klasse der Anwendung hinzu.  Spezielle Informationen zum Hinzufügen einer neuen Klasse zum Projekt, finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).  
  
 Sobald Sie die Klasse zum Projekt hinzugefügt haben, müssen Sie den Zugriff von mehreren Ansichtsklassenmember ändern.  
  
 Ändern Sie NEWVIEW.H, indem Sie den Zugriffsspezifizierer von `protected` in **public** für Konstruktor und Destruktor ändern.  Dies ermöglicht die dynamisch erstellt und zerstört wurden, Klasse, und der Ansichtsdarstellung zu ändern, bevor es sichtbar ist.  
  
 Speichern Sie die Änderungen und fahren Sie mit dem nächsten Schritt fort.  
  
##  <a name="vcconattachnewviewa3"></a> Erstellen und fügen Sie die neue Ansicht an  
 Um die neue Ansicht erstellen und anzufügen, müssen Sie die `InitInstance`\-Funktion der Anwendungsklasse ändern.  Die Änderung wird neuen Code hinzu, der ein neues Ansichtsobjekt erstellt und dann `m_pOldView` und `m_pNewView` mit den zwei vorhandenen Ansichtsobjekte initialisiert.  
  
 Da die neue Ansicht innerhalb der `InitInstance`\-Funktion, das neue erstellt und vorhandene Ansichten bestehen während der Lebensdauer der Anwendung weiter.  Es könnte die Anwendung so einfach die neue Ansicht gerade dynamisch erstellen.  
  
 Fügen Sie diesen Code nach dem Aufruf von `ProcessShellCommand` ein:  
  
 [!CODE [NVC_MFCDocViewSDI#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#3)]  
  
 Speichern Sie die Änderungen und fahren Sie mit dem nächsten Schritt fort.  
  
##  <a name="vcconswitchingfunctiona4"></a> Implementieren Sie die Vermittlungsaufgabe  
 Im vorherigen Schritt haben Sie Code hinzu, der ein neues Ansichtsobjekt erstellte und initialisierte.  Das letzte wichtige Schritt ist, die Umschaltungsmethode, `SwitchView` zu implementieren.  
  
 Am Ende der Implementierungsdatei der Anwendungsklasse \(MYWINAPP.CPP\), fügen Sie die Definition die folgende Methode hinzu:  
  
 [!CODE [NVC_MFCDocViewSDI#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#4)]  
  
 Speichern Sie die Änderungen und fahren Sie mit dem nächsten Schritt fort.  
  
##  <a name="vcconswitchingtheviewa5"></a> Fügen Sie Unterstützung zum Umschalten der Ansicht hinzu  
 Der letzte Schritt umfasst, Code hinzufügen, der die `SwitchView`\-Methode aufgerufen wird, wenn die Anwendung zwischen Ansichten wechseln muss.  Dies kann auf mehrere Arten ausgeführt werden: entweder von einem neuen Menüelement, intern hinzufügen sodass der Benutzer oder die Ansichten umschalten auswählt, sobald bestimmte Anforderungen erfüllt werden.  
  
 Weitere Informationen zum Hinzufügen von neuen und Menüelementen von Befehlshandlerfunktionen, finden Sie unter [Handler für Befehle und Verarbeiten](../mfc/handlers-for-commands-and-control-notifications.md).  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)
---
title: "MFC-Assistent zum Hinzuf&#252;gen von Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.simple.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Assistent zum Hinzufügen von Klassen"
  - "Assistenten [MFC]"
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# MFC-Assistent zum Hinzuf&#252;gen von Klassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Code\-Assistenten fügen Sie einem vorhandenen MFC\-Projekt oder einem ATL\-Projekt mit integrierter MFC\-Unterstützung eine Klasse hinzu.  Außerdem können Sie Win32\-Projekten, die über MFC\-Unterstützung verfügen, MFC\-Klassen hinzufügen.  Es hängt von den beim Erstellen des Projekts festgelegten Features ab, welche Optionen in diesem Dialogfeld verfügbar sind.  
  
## Namen  
 Geben Sie auf dieser Seite den Klassennamen, die Basisklasse und die Dateinamen für die neue Klasse an.  
  
 **Klassenname**  
 Legt den Namen der neuen Klasse fest und gibt die Standardbasis für die Namen von IDs und Dateien auf dieser Seite vor.  C\+\+\-Klassen beginnen normalerweise mit dem Buchstaben "C", so wird "CMeineKlasse" beispielsweise zu "MeineKlasse.h" usw.  
  
 **Basisklasse**  
 Gibt den Namen der Basisklasse für die neue Klasse an.  Die Basisklasse lautet standardmäßig [CWnd](../../mfc/reference/cwnd-class.md).  Durch die ausgewählte Basisklasse wird festgelegt, welche Felder auf dieser Seite aktiviert sind.  
  
 Der Typ der als Basisklasse festgelegten Klasse bestimmt, ob die Klasse über eine Dialogfeld\-ID oder eine Ressourcen\-ID verfügt.  Folgende allgemeine Klassentypen sind vorhanden:  
  
-   Klassen wie [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md) oder [CDocument](../../mfc/reference/cdocument-class.md), die keine Dialogfeld\-ID oder Ressourcen\-ID erfordern.  Diese Klassen verwenden keine Dialogfeld\- oder Ressourcen\-ID.  Wenn Sie eine dieser Klassen als Basisklasse auswählen, werden das Feld **Dialogfeld\-ID** und das Feld **DHTML\-Ressourcen\-ID** abgeblendet.  
  
-   Klassen, wie [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md) oder [CPropertyPage](../../mfc/reference/cpropertypage-class.md), für die eine Dialogfeld\-ID erforderlich ist.  
  
-   Die [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)\-Klasse, für die eine Dialogfeld\-ID, eine DHTML\-Ressourcen\-ID und ein HTML\-Dateiname erforderlich sind.  
  
 Bei Klassen, die eine Dialogfeld\-ID erfordern, kann die Dialogfeldressource eventuell schneller mit dem [Ressourcen\-Editor](../../mfc/resource-editors.md) erstellt werden, indem Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) eine ID zuweisen und anschließend eine dieser Ressourcen\-ID zugeordnete Klasse erstellen.  Weitere Informationen zum Erstellen normaler Windows\-Dialogfelder finden Sie unter [Erstellen eines neuen Dialogfelds](../../mfc/creating-a-new-dialog-box.md).  
  
> [!NOTE]
>  Wenn Sie zuerst eine Dialogressource erstellen und deren neue Klasse von `CDHtmlDialog` ableiten, löschen Sie die Windows\-Standardschaltflächen **OK** und **Abbrechen**, die im Standarddialogfeld angezeigt werden.  Das Windows\-Standarddialogfeld enthält das DHTML\-Formular, das über eigene Schaltflächen **OK** und **Abbrechen** verfügt.  
  
 Zwar kann das Dialogfeld sowohl Windows\- als auch DHTML\-Steuerelemente umfassen, von dieser Vorgehensweise wird jedoch abgeraten.  
  
 **Dialogfeld\-ID**  
 Legt die ID des Dialogfelds fest, wenn Sie `CDialog`, `CFormView`, `CPropertyPage` oder `CDHtmlDialog` als **Basisklasse** ausgewählt haben.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Objektklasse fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Klassenname** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei auswählen, wird sie vom Assistenten erst am ausgewählten Speicherort gespeichert, nachdem Sie im Assistenten auf **Fertig stellen** geklickt haben.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, die Klassendeklaration an den Inhalt der Datei anzufügen.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **.cpp\-Datei**  
 Legt für die neue Objektklasse den Namen der Implementierungsdatei fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Klassenname** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um den Dateinamen am gewünschten Speicherort zu speichern.  Die Datei wird erst am ausgewählten Speicherort gespeichert, wenn Sie im Assistenten auf **Fertig stellen** klicken.  
  
 Der Assistent ist nicht in der Lage, Dateien zu überschreiben.  Wenn Sie den Namen einer vorhandenen Datei auswählen und dann auf **Fertig stellen** klicken, werden Sie vom Assistenten gefragt, ob die Klassenimplementierung an den Inhalt der Datei angefügt werden soll.  Klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Active Accessibility**  
 Aktiviert MFC\-Unterstützung für Active Accessibility, indem [EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md) im Konstruktor aufgerufen wird.  Diese Option ist für Klassen verfügbar, die von [CWnd](../../mfc/reference/cwnd-class.md) abgeleitet sind.  
  
 **DHTML\-Ressourcen\-ID**  
 Nur für Klassen, die von `CDHtmlDialog` abgeleitet sind.  Legt die Ressourcen\-ID des DHTML\-Dialogfelds fest.  Die Ressourcen\-ID wird im HTML\-Abschnitt der projektspezifischen RC\-Datei zusammen mit dem Dateinamen des HTML\-Dialogfelds angezeigt.  Die durch diese ID identifizierte DHTML\-Ressource befindet sich in dem Dialogfeld, auf das durch **Dialogfeld\-ID** verwiesen wird.  
  
 **HTM\-Datei**  
 Nur für Klassen, die von `CDHtmlDialog` abgeleitet sind.  Legt den Namen der HTML\-Datei für das DHTML\-Dialogfeld fest.  Dieser Dateiname basiert standardmäßig auf dem Klassennamen.  Der Dateiname wird im HTML\-Abschnitt der projektspezifischen RC\-Datei zusammen mit der Ressourcen\-ID des DHTML\-Dialogfelds angezeigt.  
  
 **Automatisierung**  
 Legt die Klassenebene für die [Automatisierungsunterstützung](../../mfc/automation.md) fest.  Die Automatisierung auf Klassenebene ist für alle Klassen verfügbar, die die Automatisierung unterstützen.  Es ist auch für mit Unterstützung für Automatisierung erstellte Projekte verfügbar.  Das heißt, entweder ein MFC\-Projekt, das [ATL unterstützt](../../atl/reference/mfc-support-in-atl-projects.md), oder ein MFC\-Projekt, bei dem Sie das Kontrollkästchen **Automatisierung** auf der Seite [Erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten aktiviert haben.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Kein**|Gibt an, dass die Klasse keine Automatisierung unterstützt.|  
|**Automatisierung**|Gibt an, dass die Klasse die Automatisierung unterstützt.  Wenn Sie diese Option aktivieren, steht die neu angelegte Klasse als programmierbares Objekt für Automatisierungsclientanwendungen, wie Microsoft Visual Basic und Microsoft Excel, zur Verfügung.  Diese Option ist für die Basisklassen, die im Anschluss an diese Tabelle aufgeführt sind, nicht verfügbar.|  
|**Anhand von Typen\-ID erstellbar**|Gibt an, dass sowohl die Klasse als auch das Projekt andere Anwendungen unterstützen, die mittels Automatisierung Objekte dieser Klasse erstellen.  Mit dieser Option können Automatisierungsclients ein Automatisierungsobjekt direkt erstellen.  Die Typ\-ID im Textfeld wird von der Clientanwendung genutzt, um das zu erstellende Objekt anzugeben. Diese ID gilt systemweit und muss eindeutig sein.  Diese Option ist für die Basisklassen, die im Anschluss an diese Tabelle aufgeführt sind, nicht verfügbar.|  
  
 Für die folgenden Basisklassen ist die Automatisierungsunterstützung nicht verfügbar:  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **Typ\-ID**  
 Legt die Typ\-ID der Klasse fest.  Das Feld **Typ\-ID** verkettet den Projektnamen und den neuen Klassennamen, wie folgt: *MFCProj.MFCClass*.  Diese ID kann nur geändert werden, wenn unter **Automatisierung** die Option **Anhand von Typen\-ID erstellbar** aktiviert wurde.  
  
 **Erstellte DocTemplate\-Ressourcen**  
 Gibt an, dass die von der Anwendung erstellten Dokumente über Ressourcen für Dokumentvorlagen verfügen.  Damit dieses Kontrollkästchen aktiviert werden kann, muss das Projekt die MFC\-Dokument\-\/Ansichtarchitektur unterstützen, und die Basisklasse dieser Klasse muss [CFormView](../../mfc/reference/cformview-class.md) entsprechen.  
  
 Weitere Informationen finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Siehe auch  
 [MFC\-Klasse](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
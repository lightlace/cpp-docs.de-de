---
title: "Erweiterte Features, MFC-Anwendungs-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.advanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Anwendungs-Assistent, erweiterte Features"
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Erweiterte Features, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unter diesem Thema werden die Optionen für zusätzliche Features für Ihre Anwendung aufgeführt, zum Beispiel eine Hilfefunktion, Druckunterstützung usw.  Legen Sie in den einzelnen Abschnitten zusätzliche Unterstützungsoptionen für die erweiterten Funktionen fest.  
  
 **Kontextbezogene Hilfe \(HTML\)**  
 Generiert eine Reihe von Hilfedateien für die kontextbezogene Hilfe, die über F1 und ein Hilfemenü oder über eine **Hilfe**\-Schaltfläche in einem Dialogfeld aufgerufen werden können.  Zur Unterstützung der Hilfe ist der Hilfecompiler erforderlich.  Sie können den Hilfecompiler nachträglich installieren, indem Sie Setup erneut ausführen.  
  
 Weitere Informationen finden Sie unter [HTML\-Hilfe: Kontextbezogene Hilfe für Programme](../../mfc/html-help-context-sensitive-help-for-your-programs.md) und [Hilfedateien \(HTML\-Hilfe\)](../../ide/help-files-html-help.md).  
  
 **Drucken und Druckvorschau**  
 Erstellt den Code zur Behandlung der Druck\-, Druckeinrichtungs\- und Seitenansichtsbefehle, indem die Memberfunktionen in der [CView Class](../../mfc/reference/cview-class.md) der MFC\-Bibliothek aufgerufen werden.  Zusätzlich fügt der Assistent dem Anwendungsmenü Befehle für diese Funktionen hinzu.  Die Druckunterstützung ist nur für Anwendungen verfügbar, für die auf der Seite[Anwendungstyp, MFC\-Anwendungs\-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) des Assistenten die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert wurde.  Dokument\-\/Ansichtsanwendungen verfügen standardmäßig über Druckunterstützung.  
  
 **Automatisierung**  
 Gibt an, dass in der Anwendung Objekte bearbeitet werden können, die in einer anderen Anwendung implementiert wurden, bzw. stellt der Anwendung Automatisierungsclients zur Verfügung.  
  
 **ActiveX\-Steuerelemente**  
 Unterstützt ActiveX\-Steuerelemente \(Standard\).  Wenn Sie diese Option nicht auswählen, jedoch zu einem späteren Zeitpunkt ActiveX\-Steuerelemente in das Projekt einfügen möchten, müssen Sie der [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)\-Memberfunktion der Anwendung einen Aufruf von [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md) hinzufügen.  
  
 **MAPI \(Messaging\-API\)**  
 Gibt an, dass der Benutzer in der Anwendung E\-Mail\-Nachrichten erstellen, bearbeiten, übertragen und speichern kann.  
  
 **Windows\-Sockets**  
 Unterstützt Windows\-Sockets, mit denen Sie Anwendungen schreiben können, die über TCP\/IP\-Netzwerke kommunizieren.  
  
 **Aktive Eingabehilfe**  
 Fügt für Klassen, die von [CWnd](http://msdn.microsoft.com/library/windows/desktop/dd318466) abgeleitet sind, Unterstützung für [IAccessible](../../mfc/reference/cwnd-class.md) hinzu. Auf diese Weise können Sie die Benutzeroberfläche anpassen, um eine bessere Interaktion mit Barrierefreiheitsclients zu gewährleisten.  
  
 **Allgemeines Steuerelementmanifest**  
 Standardmäßig aktiviert.  Erstellt ein Anwendungsmanifest zur Aktivierung der im Lieferumfang von Microsoft Windows XP und von neueren Betriebssystemen enthaltenen DLL für allgemeine Steuerelemente.  
  
 Version 6 der DLL für allgemeine Steuerelemente aktualisiert die Vorläuferversion eines allgemeinen Steuerelements, das von einer vorhandenen Anwendung verwendet wird, nicht automatisch.  Um die DLL für allgemeine Steuerelemente, Version 6, verwenden zu können, müssen Sie ein Anwendungsmanifest erstellen, das Ihre Anwendung anweist, die neue DLL zu laden.  Die DLL für allgemeine Steuerelemente unterstützt auch Windows XP\-Designs.  
  
 Durch ein Anwendungsmanifest können auch andere, von Ihrer Anwendung benötigte DLLs und Versionen festgelegt werden.  Weitere Informationen über Anwendungsmanifeste finden Sie unter [Isolierte Anwendungen und parallele Assemblys](http://msdn.microsoft.com/library/dd408052) im [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 **Unterstützung für Neustart\-Manager**  
 Fügt Unterstützung für den [Neustart\-Manager von Windows](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx).  Dieses Video zeigt, wie Sie den Neustart\-Manager von MFC aus verwenden: [Verwenden des neuen Neustart\-Managers](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Erweiterte Framebereiche**  
 |Option|Beschreibung|  
|------------|------------------|  
|**Andockbarer Explorer\-Bereich**|Erstellt einen andockbaren Bereich, der dem Visual Studio **Projektmappen\-Explorer** links vom Hauptrahmenfenster ähnelt.|  
|**Andockbarer Ausgabebereich**|Erstellt einen andockbaren Bereich, der dem Visual Studio **Ausgabe**\-Bereich unter dem Hauptrahmenfenster ähnelt.|  
|**Andockbarer Eigenschaftenbereich**|Erstellt einen andockbaren Bereich, der dem Visual Studio **Eigenschaften**\-Bereich rechts vom Hauptrahmenfenster ähnelt.|  
|**Navigationsbereich**|Erstellt einen andockbaren Bereich, der der Outlook\-Navigationsleiste links vom Hauptrahmenfenster ähnelt.|  
|**Titelleiste**|Erstellt eine Titelleiste im Office\-Stil über dem Hauptrahmenfenster.|  
  
 **Anzahl der Dateien in der Liste zuletzt geöffneter Dateien**  
 Gibt die Anzahl der Dateien an, die in der Liste der zuletzt verwendeten Dateien angezeigt werden soll.  Die Anzahl beträgt standardmäßig 4.  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)
---
title: "Unterschiede beim Programmieren mit Windows Forms und MFC | Microsoft Docs"
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
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], Verglichen mit MFC"
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Unterschiede beim Programmieren mit Windows Forms und MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den Themen unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md) wird die MFC\-Unterstützung für Windows Forms beschrieben.  Wenn Sie mit .NET Framework oder MFC nicht vertraut sind, bietet Ihnen dieses Thema Hintergrundinformationen zu den Unterschieden zwischen diesen beiden Arten der Programmierung.  
  
 Windows Forms dient dem Erstellen von Microsoft Windows\-Anwendungen in .NET Framework.  Dieses Framework stellt eine moderne, objektorientierte und erweiterbare Auswahl von Klassen bereit, mit denen Sie umfangreiche Windows\-Anwendungen entwickeln können.  Windows Forms bieten die Möglichkeit, eine vielseitige Clientanwendung zu erstellen, die auf eine Vielzahl von Datenquellen zugreifen kann und mithilfe von Windows Forms\-Steuerelementen die Datenanzeige und \-bearbeitung ermöglicht.  
  
 Wenn Sie jedoch mit MFC vertraut sind, sind Sie es möglicherweise gewohnt, bestimmte Anwendungstypen zu erstellen, die von Windows Forms noch nicht ausdrücklich unterstützt werden.  Windows Forms\-Anwendungen sind gleichwertig mit MFC\-Dialoganwendungen.  Sie bieten jedoch nicht die Infrastruktur für die direkte Unterstützung anderer MFC\-Anwendungstypen wie OLE\-Documentserver\/\-container oder ActiveX\-Dokumente, bzw. zur Unterstützung der Dokument\-\/Ansichtarchitektur für SDI\- \(Single\-Document Interface\), MDI\- \(Multiple\-Document Interface\) und MTI\-Anwendungen \(Multiple Top\-Level Interface\).  Diese Anwendungen können jedoch mithilfe einer selbst programmierten Logik erstellt werden.  
  
 Weitere Informationen über Windows Forms\-Anwendungen finden Sie unter [Einführung in Windows Forms](../Topic/Windows%20Forms%20Overview.md).  
  
 Eine Beispielanwendung, in der Windows Forms angezeigt werden, die mit MFC verwendet werden, finden Sie im Artikel zur [Integration von MFC und Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Zu den folgenden Ansichts\- oder Dokument\- und Befehlsroutingfeatures von MFC bestehen keine Äquivalente in Windows Forms:  
  
-   Shellintegration  
  
     Befehle für den dynamischen Datenaustausch \(DDE, Dynamic Data Exchange\) und Befehlszeilenargumente, die von der Shell verwendet werden, wenn Sie mit der rechten Maustaste auf ein Dokument klicken und Verben wie Öffnen, Bearbeiten oder Drucken auswählen, werden von MFC verarbeitet.  Windows Forms bietet keine Shellintegration und reagiert nicht auf Shellverben.  
  
-   Dokumentvorlagen  
  
     In MFC wird eine in einem Rahmenfenster \(im MDI\-, SDI\- oder MTI\-Modus\) enthaltene Ansicht durch Dokumentvorlagen mit dem geöffneten Dokument verknüpft.  Windows Forms bietet kein Äquivalent zu Dokumentvorlagen.  
  
-   Dokumente  
  
     Durch MFC werden Dokumentdateitypen registriert und der Dokumenttyp verarbeitet, sobald ein Dokument über die Shell geöffnet wird.  Windows Forms bieten keine Dokumentunterstützung.  
  
-   Dokumentzustand  
  
     Der Änderungszustand eines Dokuments wird von MFC beibehalten.  Daher werden Sie von MFC aufgefordert, das Dokument zu speichern, sobald Sie die Anwendung beenden, die letzte Ansicht schließen, in der die Anwendung enthalten ist, oder Windows beenden.  Windows Forms bieten keine gleichwertige Unterstützung.  
  
-   Befehle  
  
     Das MFC\-Konzept ist befehlsbasiert.  Über Menüleiste, Symbolleiste und Kontextmenü können stets dieselben Befehle aufgerufen werden, z. B. **Ausschneiden** und **Kopieren**.  In Windows Forms sind Befehle eng an Ereignisse eines bestimmten UI\-Elements \(z. B. eines Menüelements\) gebunden, sodass alle Befehlsereignisse explizit verknüpft werden müssen.  Mehrere Ereignisse können in Windows Forms auch mit einem einzelnen Handler verarbeitet werden.  Weitere Informationen finden Sie unter [Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](../Topic/How%20to:%20Connect%20Multiple%20Events%20to%20a%20Single%20Event%20Handler%20in%20Windows%20Forms.md).  
  
-   Befehlsrouting  
  
     Das MFC\-Befehlsrouting ermöglicht die Befehlsverarbeitung durch die aktive Ansicht bzw. das aktive Dokument.  Da ein und derselbe Befehl in verschiedenen Ansichten oftmals ein unterschiedliches Verhalten aufweist \(**Kopieren** verhält sich in der Textbearbeitungsansicht anders als in einem Grafikeditor\), müssen die Befehle von der aktiven Ansicht verarbeitet werden.  Da die aktive Ansicht von Windows Forms\-Menüs und \-Symbolleisten nicht einheitlich interpretiert wird, können Sie für **MenuItem.Click**\-Ereignisse keine unterschiedlichen Handler für die einzelnen Ansichtstypen verwenden, ohne zusätzlichen internen Code zu schreiben.  
  
-   Mechanismus zur Befehlsaktualisierung  
  
     MFC verfügt über einen Mechanismus zur Befehlsaktualisierung.  Aus diesem Grund ist die aktive Ansicht oder das aktive Dokument für den Zustand der Benutzeroberflächenelemente verantwortlich \(z. B. das Aktivieren bzw. Deaktivieren eines Menüelements oder einer Symbolleisten\-Schaltfläche sowie der Aktivierungsstatus\).  Windows Forms bieten keinen gleichwertigen Mechanismus für die Befehlsaktualisierung.  
  
## Siehe auch  
 [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms Walkthroughs](assetId:///fd44d13d-4733-416f-aefc-32592e59e5d9)
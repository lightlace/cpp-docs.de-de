---
title: "Benutzeroberfl&#228;chen-Features, MFC-Anwendungs-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.ui"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Anwendungs-Assistent, Benutzeroberflächen-Features"
ms.assetid: 59e7b829-a665-42eb-be23-3f2a36eb2dad
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Benutzeroberfl&#228;chen-Features, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Rahmen dieses Themas werden die Optionen zur Anpassung der Anzeigeoptionen für Ihre Anwendung erläutert.  Welche Benutzeroberflächen\-Features für das Projekt verfügbar sind, hängt vom Anwendungstyp ab, der auf der Seite [Anwendungstyp, MFC\-Anwendungs\-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten angegeben wurde.  Wenn Sie z. B. eine SDI\-Anwendung erstellen, können Sie keine Stile für untergeordnete Rahmen hinzufügen.  
  
 **Hauptrahmenstile**  
 Legt die Rahmenfeatures des Hauptanwendungsfensters fest.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Breiter Rahmen**|Erstellt ein Fenster mit einem Rahmen, dessen Größe veränderbar ist.  Der Standardwert.|  
|**Minimieren\-Schaltfläche**|Fügt eine Minimieren\-Schaltfläche in das Hauptrahmenfenster ein.  Der Standardwert.|  
|**Maximieren\-Schaltfläche**|Fügt eine Maximieren\-Schaltfläche in das Hauptrahmenfenster ein.  Der Standardwert.|  
|**Minimiert**|Öffnet das Hauptrahmenfenster als Symbol.|  
|**Maximiert**|Öffnet das Hauptrahmenfenster in voller Bildschirmgröße.|  
|**Systemmenü**|Fügt ein Systemmenü in das Hauptrahmenfenster ein.  Der Standardwert.|  
|**Infofeld**|Beinhaltet ein Feld **Über** für die Anwendung.  Der Benutzer kann auf dieses Feld vom Menü **Hilfe** der Anwendung aus zugreifen.  Dies ist der Standard, der nur geändert werden kann, wenn Sie auf der Seite [Anwendungstyp, MFC\-Anwendungs\-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) die Option **Auf Dialogfeldern basierend** auswählen.<br /><br /> **Hinweis** Wenn eine Option abgeblendet ist, weist dies normalerweise darauf hin, dass der Assistent die Option nicht auf das Projekt anwendet, und zwar unabhängig davon, ob das dazugehörige Kontrollkästchen aktiviert ist oder nicht.  In diesem Fall fügt der Assistent dem Projekt das Feld **Info** immer hinzu, sofern Sie nicht zuvor festlegen, dass das Projekt auf Dialogfeldern basiert und das Kontrollkästchen dann deaktivieren.|  
|**Statusleiste**|Fügt der Anwendung eine Statusleiste hinzu.  In der Statusleiste wird automatisch der Status der FESTSTELL\-, der NUM\- und der ROLLEN\-TASTE sowie eine Meldungszeile angezeigt, in der Hilfetext für Menübefehle und Symbolleisten\-Schaltflächen erscheint.  Durch Klicken auf diese Option werden auch Menübefehle hinzugefügt, mit denen die Statusleiste ein\- oder ausgeblendet werden kann.  Anwendungen verfügen standardmäßig über eine Statusleiste.  Nicht verfügbar für Anwendungstypen, die auf Dialogfeldern basieren.|  
|**Geteiltes Fenster**|Fügt eine Trennleiste ein.  Die Trennleiste unterteilt die Hauptansichten der Anwendung.  In einer MDI \(Multiple Document Interface\)\-Anwendung ist das Clientfenster des untergeordneten MDI\-Rahmens ein Splitterfenster. In einer SDI \(Single Document Interface\)\-Anwendung und einer Anwendung, die mehrere Dokumente der höchsten Ebene unterstützt, ist das Clientfenster des Hauptrahmens ein Splitterfenster.  Nicht verfügbar für Anwendungstypen, die auf Dialogfeldern basieren.|  
  
 **Untergeordnete Rahmenstile**  
 Legt das Erscheinungsbild und den anfänglichen Zustand von untergeordneten Rahmen in der Anwendung fest.  Stile für untergeordnete Rahmen sind nur für MDI\-Anwendungen verfügbar.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Untergeordnete Minimieren\-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster über eine Schaltfläche zum Minimieren verfügt \(standardmäßig aktiviert\).|  
|**Untergeordnete Maximieren\-Schaltfläche**|Gibt an, ob ein untergeordnetes Fenster über eine Schaltfläche zum Maximieren verfügt \(standardmäßig aktiviert\).|  
|**Maximiertes untergeordnetesElement**|Gibt an, ob ein untergeordnetes Fenster anfänglich maximiert angezeigt wird, indem das cs.style\-Flag **WS\_MAXIMIZE** in der [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)\-Memberfunktion von `CChildFrame` festgelegt wird.|  
  
 **Befehlsleisten \(Menü\/Symbolleiste\/Menüband\)**  
 Gibt an, ob die Anwendung Menüs, Symbolleisten und\/oder ein Menüband beinhaltet.  Nicht verfügbar für Anwendungstypen, die auf Dialogfeldern basieren.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Klassisches Menü verwenden**|Gibt an, dass die Anwendung ein klassisches, nicht ziehbares Menü enthält.|  
|**Klassische andockbare Symbolleiste verwenden**|Fügt der Anwendung eine Windows\-Standardsymbolleiste hinzu.  Die Symbolleiste enthält Schaltflächen zum Erstellen eines neuen Dokuments, zum Öffnen und Speichern von Dokumentdateien, zum Ausschneiden, Kopieren, Einfügen oder Drucken von Text und zum Wechseln in den Hilfemodus.  Durch Aktivieren dieser Option werden auch Menübefehle hinzugefügt, mit denen die Symbolleiste ein\- oder ausgeblendet werden kann.|  
|**Symbolleiste im Browser\-Stil verwenden**|Fügt der Anwendung eine Standardsymbolleiste im Stil von Internet Explorer hinzu.|  
|**Menü\- und Symbolleiste verwenden**|Gibt an, dass die Anwendung eine ziehbare Menüleiste und eine Symbolleiste enthält.|  
|**Benutzerdefinierte Symbolleisten und Bilder**|Ermöglicht dem Benutzer, zur Laufzeit die Symbolleiste und deren Symbole anzupassen.|  
|**Personalisiertes Menüverhalten**|Gibt an, ob das Menü beim Aufruf alle Optionen beinhaltet oder nur die Befehle, die der Benutzer am häufigsten verwendet.|  
|**Verwenden eines Menübands**|Verwendet in Ihrer Anwendung ein der Office 2007\-Version ähnliches Menüband anstatt einer Menüleiste oder einer Symbolleiste.|  
  
 **Dialogfeldtitel**  
 Dieser Titel wird nur in Anwendungen, die auf [CDialog Class](../../mfc/reference/cdialog-class.md) basieren, auf der Titelleiste des Dialogfelds angezeigt.  Zur Bearbeitung dieses Felds muss zunächst unter **Anwendungstyp** die Option **Auf Dialogfeldern basierend** ausgewählt werden.  Weitere Informationen finden Sie unter [Anwendungstyp, MFC\-Anwendungs\-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md).  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)
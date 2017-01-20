---
title: "Steuerleisten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlBar-Klasse, MFC-Steuerleisten"
  - "CDialogBar-Klasse, Steuerleisten"
  - "Befehlsleisten, Typen"
  - "Steuerleisten [C++]"
  - "Steuerleisten [C++], Typen"
  - "CStatusBar-Klasse, Steuerleisten"
  - "CToolBar-Klasse, Steuerleisten"
  - "Dialogleisten, Steuerleisten"
  - "MFC, Steuerleisten"
  - "Statusleisten, Steuerleisten"
  - "Symbolleisten [C++], Steuerleisten"
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Steuerleisten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"Steuerleiste" ist der allgemeine Name für Symbolleisten, Statusleisten und Dialogleisten.  MFC\-Klassen `CToolBar`, `CStatusBar`, `CDialogBar`, `COleResizeBar` und **CReBar** werden von der [CControlBar](../mfc/reference/ccontrolbar-class.md)\- Klasse, die die allgemeine Funktionalität implementiert.  
  
 Steuerleisten sind Fenster, die Zeilen aus Steuerelementen anzeigen, mit denen Benutzer Optionen auswählen, Befehle ausführen oder Programminformationen abrufen können.  Typen von Steuerleisten enthalten Dialogleisten, Symbolleisten und Statusleisten.  
  
-   Symbolleisten, in der Klasse [CToolBar](../mfc/reference/ctoolbar-class.md)  
  
-   StatusBar\-Steuerelemente, in der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md)  
  
-   Dialogleisten, in der Klasse [CDialogBar](../mfc/reference/cdialogbar-class.md)  
  
-   Infoleisten, in der Klasse [CReBar](../mfc/reference/crebar-class.md)  
  
> [!IMPORTANT]
>  Seit MFC 4.0, sind Symbolleisten, Statusleisten und QuickInfo mithilfe der Systemfunktionalität implementiert, die im comctl32.dll anstelle des vorherigen Implementierungsbesonderen zu MFC implementiert wird.  In MFC 6.0, wurde **CReBar**, die auch comctl32.dll\-Funktionalität umschließt, hinzugefügt.  
  
 Kurze Einführungen zu den Steuerleistentypen folgen.  Weitere Informationen finden Sie unter den folgenden Links.  
  
## Steuerleisten  
 Steuerleisten erhöhen groß die Verwendbarkeit eines Programms, indem die schnelle, nur einen Schritt umfassenden Befehlsaktionen bereitstellen.  `CControlBar`\-Klasse stellt die allgemeine Funktionalität aller Symbolleisten, Statusleisten und Dialogleisten.  `CControlBar` stellt die Funktionalität zum Positionieren der Steuerleiste in das übergeordnete Rahmenfenster bereit.  Da eine Steuerleiste normalerweise ein untergeordnetes Fenster eines übergeordneten Rahmenfensters ist, bietet es "gleichgeordneten" Clientansicht oder TO MDI\-Client des Rahmenfensters.  Ein Steuerleistenobjekt verwendet Informationen über Clientrechteck des übergeordneten Fensters, um sich zu positionieren.  Dann ändert es das verbleibende ClientFensterrechteck des übergeordneten Elements, sodass die Clientansicht oder MDI\-Clientfenster den Rest des Clientfensters ausfüllt.  
  
> [!NOTE]
>  Wenn eine Schaltfläche auf der Steuerleiste nicht **BEFEHL** oder **UPDATE\_COMMAND\_UI** einen Handler verfügt, deaktiviert das Framework automatisch die Schaltfläche.  
  
## Symbolleisten  
 Eine Symbolleiste ist eine Steuerleiste, die eine Zeile von geherstellten Schaltflächen anzeigt, die Befehle ausführen.  Eine Symbolleisten\-Schaltfläche zu drücken ist zum Auswählen eines Menüelements äquivalent; es ruft den gleichen Handler zugeordnet zu einem Menüelement auf, wenn dieses Menüelement dieselbe ID wie die Symbolleistenschaltfläche hat.  Diese Schaltflächen können so konfiguriert werden, um als PushButtons, Optionsfeldern oder Kontrollkästchen angezeigt werden und sich entsprechend verhalten.  Eine Symbolleiste wird normalerweise zum Anfang eines Rahmenfensters ausgerichtet, aber eine MFC\-Symbolleiste kann an jede Seite des übergeordneten Fensters oder unverankert in einem eigenen Minirahmenfenster "angedockt".  Eine Symbolleiste kann auch "nun" und Sie können seine Größe ändern und sie mit der Maus ziehen.  Eine Symbolleiste kann QuickInfo auch anzeigen, während der Benutzer die Maus über die Schaltflächen der Symbolleiste bewegt.  Eine QuickInfo ist ein sehr kleines Popupfenster, das den Zweck unmittelbar der Schaltflächen beschreibt.  
  
> [!NOTE]
>  Seit MFC 4.0, verwendet die Windows\-Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement Klasse [CToolBar](../mfc/reference/ctoolbar-class.md).  `CToolBar` enthält [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  Ältere Symbolleisten werden noch, jedoch unterstützt.  Siehe den Artikel [Symbolleisten](../mfc/mfc-toolbar-implementation.md).  
  
## Statusleisten  
 Eine Statusleiste ist eine Steuerleiste, die Textausgabebereiche enthält, oder "Indikatoren". Die Ausgabebereiche sind als Meldungszeilen und als Statusanzeigen häufig verwendet.  Meldungszeilenbeispiele enthalten die Befehlshilfemeldungszeilen, die kurz den ausgewählten Menü\- oder Symbolleistenbefehl im linken Bereich der Standardstatusleiste berücksichtigen, die vom MFC\-Anwendungs\-Assistenten erstellt wird.  Statusanzeigenbeispiele enthalten ROLLEN, NUM\- und anderen Schlüssel.  StatusBar\-Steuerelemente werden normalerweise am Ende eines Rahmenfensters ausgerichtet.  Siehe [CStatusBar](../mfc/reference/cstatusbar-class.md)\-Klasse können Sie [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md).  
  
## Dialogleisten  
 Eine Dialogleiste ist eine Steuerleiste, auf einer Dialogfeldvorlagen\-Ressource, mit der Funktionalität eines nicht modales Dialogfeld.  Dialogleisten können Windows, benutzerdefinierten oder ActiveX\-Steuerelemente enthalten.  Wie ein Dialogfeld, kann der Benutzer mit Steuerelementen angesteuert.  Dialogleisten können zur oben, unten ausgerichtet werden, linken wurde, oder rechte Seite eines Rahmenfensters und können in ihr eigenes Rahmenfenster auch lösen.  Siehe [CDialogBar](../mfc/reference/cdialogbar-class.md)\- Klasse.  
  
## Infoleisten  
 [Infoleiste](../mfc/using-crebarctrl.md) ist eine Steuerleiste, die das Andocken, Layout, Zustand und Persistenzinformationen für Infoleistensteuerelemente bereitstellt.  Ein Infoleistenobjekt kann eine Vielzahl von untergeordneten Fenstern, normalerweise weitere Steuerelemente enthalten, einschließlich Eingabefelder, Symbolleisten und Listenfelder.  Ein Infoleistenobjekt kann untergeordneten Fenster über einer angegebenen Bitmap anzeigen.  Er kann automatisch oder manuell angepasst indem auf die Ziehpunktleiste klickt oder ziehen.  Siehe [CReBar](../mfc/reference/crebar-class.md)\- Klasse.  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
---
title: "Dialogfelder | Microsoft Docs"
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
  - "CDialog-Klasse, MFC-Dialogfelder"
  - "MFC-Dialogfelder"
  - "MFC, Dialogfelder"
  - "Modale Dialogfelder, MFC-Dialogfelder"
  - "Nicht modale Dialogfelder, MFC-Dialogfelder"
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Dialogfelder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Anwendungen für Windows sind häufig den Benutzer durch Dialogfelder kommunizieren.  Klasse [CDialog\-Klasse](../mfc/reference/cdialog-class.md) stellt eine Schnittstelle zum Verwalten von Dialogfeldern bereit, nimmt der Visual C\+\+\-Dialog\-Editor es einfach, Dialogfelder entwerfen und ihre Dialogfeldvorlagenressourcen zu erstellen, und Code\-Assistenten vereinfachen den Prozess das Initialisieren und Überprüfen der Steuerelemente in einem Dialogfeld und des zum Erfassen der Werte, die vom Benutzer eingegeben werden.  
  
 Dialogfelder enthalten die Steuerelemente und umfassen:  
  
-   Allgemeine, wie Windows\-Steuerelemente Eingabefelder PushButtons, Listenfelder, Kombinationsfelder, Struktur\-Steuerelemente, Listensteuerelemente und Statusanzeigen.  
  
-   ActiveX\-Steuerelemente.  
  
-   Ownerdrawnkontrollen: Steuerelemente, die Sie für Zeichnung im Dialogfeld zuständig sind.  
  
 In den meisten Dialogfeldern werden modal, die vor der Anwendung eines anderen Teils des Programms den Benutzer erfordern, das Dialogfeld zu schließen.  Es ist möglich, nicht modale Dialogfelder zu erstellen, die Benutzer mit anderen Fenstern arbeiten, während das Dialogfeld geöffnet ist.  MFC unterstützt beide Arten Dialogfeld mit der Klasse `CDialog`.  Die Steuerelemente werden mithilfe einer Dialogfeldvorlagenressource angeordnet und verwaltet, erstellt wurde mit [Dialog\-Editor](../mfc/dialog-editor.md).  
  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md), das auch als Dialogfelder im Registerformat, Dialogfelder sind, die Seiten "" der verschiedenen Dialogfeld\-Steuerelemente enthalten.  Jede Seite verfügt einen Dateiordner "Registerkarte" oben.  Das Klicken auf eine Registerkarte im Vordergrund ruft dieser Seite des Dialogfelds.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Beispiel: Anzeigen eines Dialogfelds zum einen Menübefehl](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [Dialogfeldkomponenten im Framework](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [Modal und nicht modale Dialogfelder](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [Eigenschaftenblätter und Eigenschaftenseiten](../mfc/property-sheets-and-property-pages-mfc.md) in einem Dialogfeld  
  
-   [Erstellen der Dialogfeldressource](../mfc/creating-the-dialog-resource.md)  
  
-   [Erstellen einer Dialogfeldklasse mit Code\-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [Dialogdatenaustausch \(DDX\) und Validierung \(DDV\)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Zuordnungs\-Windows\-Meldungen zu der Klasse](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [Häufig überschriebene Memberfunktionen](../mfc/commonly-overridden-member-functions.md)  
  
-   [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)  
  
-   [Allgemeine Dialogfeldklassen](../mfc/common-dialog-classes.md)  
  
-   [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md)  
  
-   Erstellen einer Anwendung, deren Benutzeroberfläche ein Dialogfeld ist: finden Sie die [CMNCTRL1](../top/visual-cpp-samples.md) oder [CMNCTRL2](../top/visual-cpp-samples.md) ein.  Der Anwendungs\-Assistent stellt diese Option ebenfalls bereit.  
  
-   [Beispiele](../mfc/dialog-sample-list.md)  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
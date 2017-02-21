---
title: "OLE-Standarddialogfeld-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Klassen [C++]"
  - "Allgemeine Dialogfeldklassen"
  - "Dialogklassen [C++], OLE"
  - "OLE (allgemeine Dialogfeldklassen) [C++]"
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Standarddialogfeld-Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen kümmern allgemeine OLE\-Aufgaben, indem verschiedene Dialogfelder standardmäßigen OLE implementieren.  Sie stellen auch eine konsistente Benutzeroberfläche für OLE\-Funktionalität bereit.  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 Wird vom Framework, um allgemeine Implementierungen für alle OLE\-Dialogfelder zu enthalten.  Alle Dialogfeldklassen in der Benutzeroberflächekategorie werden von dieser Basisklasse abgeleitet.  `COleDialog` kann nicht direkt verwendet werden.  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 Zeigt das EINFG\-Objektdialogfeld, die Standardbenutzeroberfläche für Einfügen von neuen eingebetteten oder verknüpften Elemente OLE an.  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 Zeigt das Inhalte einfügen\-Dialogfeld, die Standardbenutzeroberfläche für das Implementieren des Bearbeitungs\-Inhalte einfügen\-Befehls an.  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Zeigt das Bearbeitungs\-Linkdialogfeld, die Standardbenutzeroberfläche für das Ändern von Informationen über verknüpfte Elemente.  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 Zeigt das Änderungs\-Symboldialogfeld, die Standardbenutzeroberfläche für das Ändern des Symbols an, das mit einem eingebetteten oder verknüpften OLE Element zugeordnet ist.  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 Zeigt das Bekehrtdialogfeld, die Standardbenutzeroberfläche für das Konvertieren von OLE\-Elementen von einem Typ zu anderen an.  
  
 [COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)  
 Kapselt das häufig verwendete OLE Eigenschaftendialogfeld Windows.  Allgemeine OLE\-Eigenschaftendialogfelder bieten eine einfache Möglichkeit, Eigenschaften eines OLE\-Dokumentelements anzuzeigen und zu ändern, das mit Windows\-Standards in ähnlicher Weise konsistent ist.  
  
 [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)  
 Zeigt das Updatedialogfeld, die Standardbenutzeroberfläche für das Aktualisieren aller Links in einem Dokument an.  Das Dialogfeld enthält eine Statusanzeige, um anzugeben, wie nahe die Updateprozedur abgeschlossen ist.  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 Zeigt das Änderungs\-Quelldialogfeld, die Standardbenutzeroberfläche für das Ändern des Ziels oder der Quelle eines Links an.  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 Zeigt den Server ausgelastete und des Servers nicht Reaktionsdialogfelder, die Standardbenutzeroberfläche für die Behandlung der Aufrufe von ausgelasteten Anwendungen an.  Normalerweise automatisch angezeigt durch die `COleMessageFilter` \- Implementierung.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)
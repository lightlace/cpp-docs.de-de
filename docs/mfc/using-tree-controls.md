---
title: "Verwenden von Struktursteuerelementen"
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
  - "CTreeCtrl-Klasse, Verwenden"
  - "Struktursteuerelemente, Informationen über Struktur-Steuerelemente"
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Struktursteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typische Verwendungen einer Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) entspricht dem Muster unten:  
  
-   Das Steuerelement wird erstellt.  Wenn das Steuerelement in einer Dialogfeldvorlage angegeben ist, oder wenn Sie `CTreeView` verwenden, ist die Erstellung automatisch, wenn das Dialogfeld oder Ansicht erstellt wird.  Wenn Sie in der Strukturansicht als untergeordnetes Fenster eines anderen Fensters erstellen möchten, verwenden Sie die [Erstellen](../Topic/CTreeCtrl::Create.md)\-Memberfunktion.  
  
-   Wenn Sie das Struktursteuerelement Bilder verwenden, legen Sie eine Bildliste fest, indem Sie [SetImageList](../Topic/CTreeCtrl::SetImageList.md) aufrufen.  Sie können den Einzug ändern, indem Sie [SetIndent](../Topic/CTreeCtrl::SetIndent.md) aufrufen.  Eine gute Zeit, hierzu ist in [OnInitDialog](../Topic/CDialog::OnInitDialog.md) \(für Steuerelemente in Dialogfeldern\) oder [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) \(für Ansichten\).  
  
-   Fügen Sie Daten in das Steuerelement, indem Sie sie einmal die Funktion `CTreeCtrl`[InsertItem](../Topic/CTreeCtrl::InsertItem.md) für jedes Datenelement aufrufen.  `InsertItem` gibt ein Handle für das Element, das Sie verwenden können, um es später zu verweisen, wie zurück, wenn es untergeordneten Elemente hinzufügt.  Eine gute Zeit, die Daten zu initialisieren ist in `OnInitDialog` \(für Steuerelemente in Dialogfeldern\) oder `OnInitialUpdate` \(für Ansichten\).  
  
-   Wenn der Benutzer das Steuerelement verwendet, sendet es verschiedene Benachrichtigungsmeldungen.  Sie können eine Funktion angeben, um alle der Meldungen zu bearbeiten, die Sie bearbeiten möchten, indem Sie einen **ON\_NOTIFY\_REFLECT**\-Makro in der Meldungszuordnung des Steuerfensters hinzufügen oder ein `ON_NOTIFY`\-Makro zur Meldungszuordnung des übergeordneten Fensters hinzufügen.  Siehe [Strukturansicht\-Steuerelement\-Benachrichtigungsmeldungen](../mfc/tree-control-notification-messages.md) weiter unten in diesem Thema für eine Liste möglicher Benachrichtigungen.  
  
-   Rufen Sie die verschiedenen Funktionen des festgelegten Members zum Festlegen von Werten für das Steuerelement auf.  Ändert, dass Sie die Include ausführen können, das den Einzug festgelegt und der Text, das Bild oder die Daten zugeordnet werden mit einem Element ändert.  
  
-   Verwenden Sie die verschiedenen Funktionen abrufen, um den Inhalt des Steuerelements sicherzustellen.  Sie können den Inhalt des Strukturansicht\-Steuerelements mit Funktionen auch durchlaufen, die es ermöglichen, Handles zu übergeordneten Elementen, zu untergeordneten Elementen und den Geschwistern eines bestimmten Elements abzurufen.  Sie können die untergeordneten Elemente eines bestimmten Knotens sogar sortieren.  
  
-   Wenn Sie mit dem Steuerelement verwenden, stellen Sie sicher, dass er ordnungsgemäß gelöscht wird.  Wenn dem Tree\-Steuerelement in einem Dialogfeld ist, oder wenn es eine Ansicht ist, werden diese und das `CTreeCtrl`\-Objekt automatisch zerstört.  Falls nicht, müssen Sie sicherstellen, dass das Steuerelement und das `CTreeCtrl`\-Objekt ordnungsgemäß gelöscht werden.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
---
title: "Erstellen eines CToolBarCtrl-Objekts"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CToolBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl-Klasse, Erstellen von Symbolleisten"
  - "Symbolleisten-Steuerelemente [MFC], Erstellen"
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
caps.latest.revision: 11
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines CToolBarCtrl-Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)\-Objekte enthalten einige interne Datenstrukturen \- Eine Liste von Schaltflächensymbolbitmaps, eine Liste von Schaltflächenbezeichnungszeichenfolgen und eine Liste von `TBBUTTON`\-Strukturen dieser Mitarbeiter ein Bild und\/oder eine Zeichenfolge mit der Position, Schriftschnitt, den Zustand und der Befehls\-ID der Schaltfläche.  Jedes der Elemente dieser Datenstrukturen ist durch einen nullbasierten Index verwiesen.  Bevor Sie ein `CToolBarCtrl`\-Objekt verwenden können, müssen Sie dieser Datenstrukturen installieren.  Eine Liste der Datenstrukturen, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Symbolleisten\-Steuerelemente](https://msdn.microsoft.com/en-us/library/47xcww9x.aspx).  Die Liste von Zeichenfolgen kann für Schaltflächenbezeichnungen nur verwendet werden; Sie können Zeichenfolgen nicht der Symbolleiste abrufen.  
  
 Um ein `CToolBarCtrl`\-Objekt zu verwenden, führen Sie normalerweise folgende Schritte:  
  
### Um ein CToolBarCtrl\-Objekt verwenden  
  
1.  Erstellen Sie das Objekt unter [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md).  
  
2.  Rufen Sie [Erstellen](../Topic/CToolBarCtrl::Create.md) auf, um die Windows\-Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement zu erstellen und auf das Objekt `CToolBarCtrl` anzufügen.  Wenn Sie für Bitmapbilder Schaltflächen soll, fügen Sie den Schaltflächenbitmaps der Symbolleiste hinzu, indem Sie [AddBitmap](../Topic/CToolBarCtrl::AddBitmap.md) aufrufen.  Wenn Sie Zeichenfolgenbezeichnungen für Schaltflächen soll, fügen Sie den Zeichenfolgen der Symbolleiste hinzu, indem Sie [AddString](../Topic/CToolBarCtrl::AddString.md) oder [AddStrings](../Topic/CToolBarCtrl::AddStrings.md) aufrufen.  Nachdem Sie `AddString` und\/oder `AddStrings` aufgerufen haben, können Sie [Automatisch anpassen](../Topic/CToolBarCtrl::AutoSize.md) aufrufen, um die Zeichenfolge oder die Zeichenfolgen abzurufen, der angezeigt wird.  
  
3.  Fügen Sie Schaltflächenstrukturen der Symbolleiste hinzu, indem Sie [AddButtons](../Topic/CToolBarCtrl::AddButtons.md) aufrufen.  
  
4.  Wenn Sie QuickInfos soll, Handle **TTN\_NEEDTEXT** Meldungen im Besitzerfenster der Symbolleiste, wie in [Behandlungs\-QuickInfo\-Benachrichtigungen](../mfc/handling-tool-tip-notifications.md) beschrieben.  
  
5.  Wenn Sie den Benutzern ermöglichen möchten, die Symbolleiste anpassen, Handleanpassungsbenachrichtigungsmeldungen im Besitzerfenster, wie in [Behandlungs\-Anpassungs\-Benachrichtigungen](../mfc/handling-customization-notifications.md) beschrieben.  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
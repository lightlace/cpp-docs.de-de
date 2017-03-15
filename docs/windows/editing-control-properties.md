---
title: "Editing Control Properties | Microsoft Docs"
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
  - "controls [C++], undoing changes"
  - "controls [C++], editing properties"
  - "dialog box controls, editing properties"
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Editing Control Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So bearbeiten Sie die Eigenschaften eines oder mehrerer Steuerelemente  
  
1.  Wählen Sie im Dialogfeld das Steuerelement aus, das Sie ändern möchten.  
  
    > [!NOTE]
    >  Wenn mehrere Steuerelemente ausgewählt werden, können nur die gemeinsamen Eigenschaften der ausgewählten Steuerelemente bearbeitet werden.  
  
2.  Ändern Sie die Steuerelementeigenschaften im [Eigenschaftenfenster](../Topic/Properties%20Window.md).  
  
    > [!NOTE]
    >  Wenn Sie für die **Bitmap**\-Eigenschaft eines Schaltflächen\-, Optionsfeld\- oder Kontrollkästchen\-Steuerelements den Wert **True** festlegen, wird das Format BS\_BITMAP für das Steuerelement implementiert.  Weitere Informationen finden Sie unter [Button Styles](../mfc/reference/button-styles.md) \(nur auf Englisch verfügbar\).  Ein Beispiel für das Verknüpfen einer Bitmap mit einem Steuerelement finden Sie unter [CButton::SetBitmap](../Topic/CButton::SetBitmap.md).  Im Dialogressourcen\-Editor werden keine Bitmaps auf den Steuerelementen angezeigt.  
  
### So machen Sie Änderungen an Steuerelementeigenschaften rückgängig  
  
1.  Stellen Sie sicher, dass das Steuerelement im Dialog\-Editor den Fokus besitzt.  
  
2.  Klicken Sie im Menü **Bearbeiten** auf **Rückgängig** \(befindet sich der Fokus nicht auf dem Steuerelement, ist der Befehl **Rückgängig** nicht verfügbar\).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)
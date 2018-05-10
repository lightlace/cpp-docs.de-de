---
title: Bearbeiten von Steuerelementeigenschaften | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f7976f74e9454b023c4da51168fa780ccaea2342
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="editing-control-properties"></a>Bearbeiten von Steuerelementeigenschaften
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>So bearbeiten Sie die Eigenschaften eines Steuerelements oder Steuerelemente  
  
1.  Wählen Sie das Steuerelement, das Sie ändern möchten, klicken Sie im Dialogfeld.  
  
    > [!NOTE]
    >  Wenn Sie mehrere Steuerelemente auswählen, können nur die Eigenschaften der ausgewählten Steuerelementen gemeinsam bearbeitet werden.  
  
2.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften des Steuerelements.  
  
    > [!NOTE]
    >  Beim Festlegen der **Bitmap** -Eigenschaft für eine Schaltfläche, Optionsfeld oder gleich Kontrollkästchensteuerelement **"true"**, den Stil BS_BITMAP für das Steuerelement implementiert wird. Weitere Informationen finden Sie unter [Schaltflächenstile](../mfc/reference/styles-used-by-mfc.md#button-styles). Ein Beispiel für eine Bitmap mit einem Steuerelement zuordnen, finden Sie unter [CButton:: SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bitmaps werden nicht auf das Steuerelement angezeigt, während Sie im Dialogfeld Ressourcen-Editor sind.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Zum Rückgängigmachen von Änderungen an den Eigenschaften eines Steuerelements  
  
1.  Stellen Sie sicher, dass das Steuerelement in Dialog-Editor den Fokus besitzt.  
  
2.  Wählen Sie **rückgängig zu machen** aus der **bearbeiten** im Menü (wenn der Fokus nicht auf das Steuerelement ist die **rückgängig zu machen** Befehl ist nicht verfügbar).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)


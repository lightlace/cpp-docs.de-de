---
title: Bearbeiten von Steuerelementeigenschaften | Microsoft-Dokumentation
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
- dialog box controls [C++], editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f0f387f536e5d1762f3c48a1955b5053e144e3bc
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082857"
---
# <a name="editing-control-properties"></a>Bearbeiten von Steuerelementeigenschaften

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>So bearbeiten Sie die Eigenschaften eines Steuerelements oder-Steuerelemente

1. Wählen Sie das Steuerelement, die, das Sie ändern möchten, klicken Sie im Dialogfeld.

   > [!NOTE]
   > Wenn Sie mehrere Steuerelemente auswählen, können nur die Eigenschaften, die die ausgewählten Steuerelemente gemeinsam bearbeitet werden.

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften des Steuerelements.

   > [!NOTE]
   > Beim Festlegen der **Bitmap** -Eigenschaft für eine Schaltfläche, Optionsfeld oder Kontrollkästchen-Steuerelement gleich **"true"**, den Stil BS_BITMAP für das Steuerelement implementiert wird. Weitere Informationen finden Sie unter [Button-Stile](../mfc/reference/styles-used-by-mfc.md#button-styles). Ein Beispiel für eine Bitmap mit einem Steuerelement zuordnen, finden Sie unter [CButton:: SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bitmaps werden nicht auf das Steuerelement angezeigt, während Sie auf die **Dialogfeld** Ressourcen-Editor.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Um Änderungen an den Eigenschaften eines Steuerelements rückgängig zu machen.

1. Stellen Sie sicher, dass das Steuerelement den Fokus besitzt, der **Dialogfeld** Editor.

2. Wählen Sie **rückgängig zu machen** aus der **bearbeiten** Menü (ist den Fokus nicht auf das Steuerelement, das **rückgängig zu machen** Befehl nicht verfügbar).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)
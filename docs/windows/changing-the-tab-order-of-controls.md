---
title: "Ändern der Aktivierreihenfolge von Steuerelementen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dca6b1bb894aa2219a0352ba9c359e6f3c5a4677
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-tab-order-of-controls"></a>Ändern der Aktivierreihenfolge von Steuerelementen
Die Aktivierreihenfolge ist die Reihenfolge, in der die TAB-Taste den Eingabefokus von einem Steuerelement zum nächsten in einem Dialogfeld wird verschoben. In der Regel geht die Tab-Reihenfolge von links nach rechts und von oben nach unten in einem Dialogfeld. Jedes Steuerelement verfügt über eine **Tabstop** -Eigenschaft, die bestimmt, ob ein Steuerelement den Eingabefokus erhält.  
  
### <a name="to-set-input-focus-for-a-control"></a>Eingabefokus für ein Steuerelement festlegen.  
  
1.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)Option **"true"** oder **"false"** in der **Tabstop** Eigenschaft.  
  
 Auch Steuerelemente, die nicht die Tabstop-Eigenschaft auf "true" muss als Teil der Aktivierreihenfolge festgelegt haben. Dies kann wichtig sein, z. B., wenn Sie [definieren Zugriffstasten (Mnemonik)](../windows/defining-mnemonics-access-keys.md) für Steuerelemente, die keine Beschriftungen aufweisen. Statischer Text, der eine Zugriffstaste für eine verwandte Steuerelement enthält muss die dazugehörigen Steuerelement in der Aktivierreihenfolge unmittelbar vorangestellt sein.  
  
> [!NOTE]
>  Wenn das Dialogfeld überlappende Steuerelemente enthält, kann durch das Ändern der Aktivierreihenfolge die Gruppierung ändern, auf dem die Steuerelemente angezeigt werden. Steuerelemente, die weiter unten in der Aktivierreihenfolge stammen werden immer auf alle überlappende Steuerelemente angezeigt, die ihnen in der Aktivierreihenfolge vorausgehen.  
  
#### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Anzeigen die aktuellen Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld  
  
1.  Auf der **Format** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
 \- oder –  
  
-   Drücken Sie STRG + d  
  
#### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>So ändern Sie die Reihenfolge der Registerkarten für alle Steuerelemente in einem Dialogfeld  
  
1.  Auf der **Format** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
     Eine Zahl in der oberen linken Ecke der einzelnen Steuerelemente zeigt seine Position in der aktuellen Aktivierreihenfolge.  
  
2.  Legen Sie die Reihenfolge der Registerkarten durch Klicken auf jedes Steuerelement in der Reihenfolge möchten, führen die TAB-Taste.  
  
3.  Drücken Sie **EINGABETASTE** beenden **Aktivierreihenfolge** Modus.  
  
    > [!TIP]
    >  Sobald Sie Aktivierreihenfolge Modus eingegeben haben, drücken Sie ESC-Taste oder die EINGABETASTE, um die Möglichkeit zum Ändern der Aktivierreihenfolge zu deaktivieren.  
  
#### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>So ändern Sie die Reihenfolge der Registerkarten für zwei oder mehr Steuerelemente  
  
1.  Aus der **Format** Menü wählen **Aktivierreihenfolge**.  
  
2.  Geben Sie an, die Änderung in der Reihenfolge, in denen beginnt. Halten Sie sich zu diesem Zweck die **STRG** Taste, und klicken Sie auf das Steuerelement vor diejenige, in dem Sie die Reihenfolge geänderte, um zu beginnen.  
  
     Beispielsweise, wenn Sie die Reihenfolge der Steuerelemente 7 bis 9 ändern möchten, halten Sie STRG GEDRÜCKT, und wählen Sie dann Steuerelement 6 zuerst.  
  
    > [!NOTE]
    >  Doppelklicken Sie auf das Steuerelement, um ein bestimmtes Steuerelement Nummer 1 (zuerst in der Aktivierreihenfolge) festzulegen.  
  
3.  Lassen Sie die STRG-Taste, und klicken Sie auf die Steuerelemente in der Reihenfolge an, dass Sie die TAB-Taste, um von diesem Punkt folgen soll.  
  
4.  Drücken Sie **EINGABETASTE** beenden **Aktivierreihenfolge** Modus.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


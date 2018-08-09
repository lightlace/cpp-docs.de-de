---
title: Ändern der Aktivierreihenfolge von Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], tab order
- focus, tab order
- tab controls, tab order
- Tabstop property for controls
- controls [C++], focus
- dialog box controls, tab order
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32368ca6731c53255587a2083c9fe685eb8fefd0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641846"
---
# <a name="changing-the-tab-order-of-controls"></a>Ändern der Aktivierreihenfolge von Steuerelementen
Die Aktivierreihenfolge ist die Reihenfolge, in der **Registerkarte** -Taste wird den Eingabefokus von einem Steuerelement verschoben, an den nächsten in einem Dialogfeld. In der Regel wird die Aktivierreihenfolge auf, von links nach rechts und von oben nach unten in einem Dialogfeld. Jedes Steuerelement verfügt über eine **Tabstop** -Eigenschaft, die bestimmt, ob ein Steuerelement den Eingabefokus erhält.  
  
### <a name="to-set-input-focus-for-a-control"></a>Eingabefokus für ein Steuerelement festgelegt.  
  
1.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)Option **"true"** oder **"false"** in die **Tabstop** Eigenschaft.  
  
 Selbst Steuerelemente, die keine der **Tabstop** -Eigenschaftensatz auf **"true"** müssen Teil der Aktivierreihenfolge. Dies kann wichtig sein, z. B., wenn Sie [definieren Sie Zugriffstasten (mnemonischen Zeichen)](../windows/defining-mnemonics-access-keys.md) für Steuerelemente, die keine Beschriftungen. Statischer Text, der eine Zugriffstaste für ein verwandtes Steuerelement enthält muss das zugehörige Steuerelement in der Aktivierreihenfolge unmittelbar vorangestellt sein.  
  
> [!NOTE]
>  Wenn das Dialogfeld überlappende Steuerelemente enthält, unter Umständen ändern der Aktivierreihenfolge verändern, wie die Steuerelemente angezeigt werden. Steuerelemente, die weiter unten in der Aktivierreihenfolge erläutert werden immer auf überlappende Steuerelemente angezeigt, die ihnen in der Aktivierreihenfolge vorausgehen.  
  
### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Anzeigen die aktuellen Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld  
  
1.  Auf der **Format** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
 \- oder –  
  
-   Drücken Sie **STRG**+**D**.  
  
### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>So ändern Sie die Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld  
  
1.  Auf der **Format** Menü klicken Sie auf **Aktivierreihenfolge**.  
  
     Eine Zahl in der oberen linken Ecke der einzelnen Steuerelemente zeigt seine Position in der aktuellen Aktivierreihenfolge.  
  
2.  Festlegen der Aktivierreihenfolge durch Klicken auf jedes Steuerelement in der gewünschten Reihenfolge der **Registerkarte** Schlüssel folgen.  
  
3.  Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.  
  
    > [!TIP]
    >  Nach der Eingabe **Aktivierreihenfolge** -Modus können Sie durch Drücken **Esc** oder **EINGABETASTE** So deaktivieren Sie die Möglichkeit zum Ändern der Aktivierreihenfolge.  
  
### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>So ändern Sie die Aktivierreihenfolge für zwei oder mehr Steuerelementen  
  
1.  Von der **Format** Menü wählen **Aktivierreihenfolge**.  
  
2.  Geben Sie die Änderung in der Reihenfolge, in denen beginnt. Dazu halten Sie die **STRG** gedrückt, und klicken Sie auf das Steuerelement vor dem ersten, die Reihenfolge geänderte werden sollen.  
  
     Z. B., wenn Sie die Reihenfolge der Steuerelemente ändern möchten `7` über `9`, halten Sie die **STRG**, wählen Sie dann das Steuerelement `6` erste.  
  
    > [!NOTE]
    >  Für ein bestimmtes Steuerelement festzulegen, Anzahl `1` (zuerst in der Aktivierreihenfolge), doppelklicken Sie auf das Steuerelement.  
  
3.  Version der **STRG** Schlüssel, und klicken Sie dann die Steuerelemente in der gewünschten Reihenfolge der **Registerkarte** -Taste, um von diesem Punkt folgen.  
  
4.  Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
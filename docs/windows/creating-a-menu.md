---
title: Erstellen eines Menüs (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.menu
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
- menus [C++], adding items
- commands [C++], adding to menus
- menu items, adding to menus
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
ms.openlocfilehash: 438480032f1fe9208e406b4ee499267e42148a48
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702803"
---
# <a name="creating-a-menu-c"></a>Erstellen eines Menüs (C++)

> [!NOTE]
> Die **Ressourcen-Fenster** ist in Express-Editionen nicht verfügbar.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü

1. Von der **Ansicht** , wählen Sie im Menü **Ressourcenansicht** , und klicken Sie dann mit der rechten Maustaste auf die **Menü** Überschrift, und wählen Sie **Ressource hinzufügen**. Wählen Sie **Menü**aus.

1. Wählen Sie auf der Menüleiste das Feld **Neues Element** (das Rechteck mit dem Text "Hier eingeben") aus.

   ![Feld "Neues Element" im Menü-Editor](../windows/media/vcmenueditornewitembox.gif "VcMenuEditorNewItemBox")<br/>
   Feld "Neues Element"

1. Geben Sie einen Namen für das neue Menü ein, z. B. "Datei".

   Der eingegebene Text wird sowohl im **Menü** -Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)angezeigt. Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.

   Nachdem Sie das neue Menü in der Menüleiste benannt haben, rückt das Feld für das neue Menüelement nach rechts (damit ein weiteres Menü eingefügt werden kann). Unter dem ersten Menü wird ein weiteres Feld geöffnet, dem Sie Menübefehle hinzufügen können.

   ![Erweiterte neue Elementfeld](../windows/media/vcmenueditornewitemboxexpanded.gif "VcMenuEditorNewItemBoxExpanded")<br/>
   Feld "Neues Element", dessen Fokus nach der Eingabe des Menünamens versetzt wurde

   > [!NOTE]
   > Um ein einzelnes Element im Menü auf der Menüleiste zu erstellen, legen die **Popup** Eigenschaft **"false"**.

## <a name="to-insert-a-new-menu-between-existing-menus"></a>So fügen Sie ein neues Menüs zwischen vorhandenen Menüs ein

Wählen Sie einen vorhandenen Menünamen, und drücken Sie die **einfügen** Schlüssel. Die **neues Element** Feld vor dem ausgewählten Element eingefügt wird.

   \- oder –

Mit der rechten Maustaste in der Menüleiste, und wählen Sie **neue einfügen** aus dem Kontextmenü.

## <a name="to-add-commands-to-a-menu"></a>So fügen Sie Befehle zu einem Menü hinzu

1. Erstellen Sie ein Menü an.

1. Wählen Sie einen Menünamen, z. B. **Datei**.

   Jedes Menü wird erweitert, und es wird ein neues Elementfeld für Befehle zur Verfügung gestellt. Sie können z. B. die Befehle hinzufügen **neu**, **öffnen**, und **schließen** auf eine **Datei** Menü.

1. Geben Sie im neuen Elementfeld einen Namen für den neuen Menübefehl ein.

   > [!NOTE]
   > Der eingegebene Text wird sowohl im **Menü** -Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)angezeigt. Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.

   > [!TIP]
   > Sie können eine mnemonische Taste (Zugriffstaste) definieren, die dem Benutzer ermöglicht, den Menübefehl auszuwählen. Geben Sie ein kaufmännisches und-Zeichen (`&`) vor einen Buchstaben ein, um ihn als mnemonisch anzugeben. Der Benutzer kann den Menübefehl auswählen, indem er diesen Buchstaben eingibt.

1. In der **Eigenschaften** wählen Sie im Fenster Eigenschaften, die gelten für den Menübefehl. Weitere Informationen finden Sie unter [Menübefehlseigenschaften](../windows/menu-command-properties.md).

1. In der **Eingabeaufforderung** im Feld der **Eigenschaften** Fenster, geben Sie die eingabeaufforderungs-Zeichenfolge in der Statusleiste Ihrer Anwendung angezeigt werden sollen.

   Dieser Schritt erstellt einen Eintrag in der Tabelle mit den gleichen Ressourcenbezeichner des Menübefehls, die Sie erstellt haben.

   > [!NOTE]
   > Eingabeaufforderungen können nur auf Menüelemente mit Anwenden einer **Popup** Eigenschaft **"true"**. Beispielsweise können Menüelemente auf oberster Ebene über Eingabeaufforderungen verfügen, wenn sie über Untermenüelemente verfügen. Der Zweck einer **Eingabeaufforderung** besteht darin anzugeben, was passiert, wenn ein Benutzer das Menüelement auswählt.

1. Drücken Sie **EINGABETASTE** auf den Menübefehl abzuschließen.

   Das neue Elementfeld wird ausgewählt, sodass Sie zusätzliche Menübefehle erstellen können.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)
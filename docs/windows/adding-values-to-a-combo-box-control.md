---
title: Hinzufügen von Werten zu einem Kombinationsfeld-Steuerelement
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
ms.openlocfilehash: 5df37a14809a41166b713f946b4f1abc19ea1ff4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570377"
---
# <a name="adding-values-to-a-combo-box-control"></a>Hinzufügen von Werten zu einem Kombinationsfeld-Steuerelement

Sie können Werte an ein Kombinationsfeld-Steuerelement hinzufügen, solange Sie haben die **Dialogfeld** Editor öffnen.

> [!TIP]
> Es ist eine gute Idee, alle Werte im Kombinationsfeld hinzufügen *vor* Sie seine Größe im der **Dialogfeld** -Editor, oder Sie können truncate Text, der im Kombinationsfeld-Steuerelement angezeigt werden soll.

### <a name="to-enter-values-into-a-combo-box-control"></a>Um die Werte in einem Kombinationsfeld-Steuerelement eingeben

1. Wählen Sie das Kombinationsfeld-Steuerelement, indem Sie darauf klicken.

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), führen Sie einen Bildlauf nach unten, um die **Daten** Eigenschaft.

   > [!NOTE]
   > Wenn Sie Eigenschaften gruppiert nach Typ anzeigen **Daten** wird in der **Verschiedenes** Eigenschaften.

3. Klicken Sie in den Wertebereich für die **Daten** Eigenschaft, und geben die Datenwerte, die durch Semikolons getrennt sind.

   > [!NOTE]
   > Stellen Sie nicht zwischen den Werten Leerzeichen stehen, da Leerzeichen in der Dropdown Liste verfälschen.

4. Klicken Sie auf **EINGABETASTE** Sie abschließend Werte hinzufügen.

Informationen dazu, wie den Dropdown-Teil eines Kombinationsfelds vergrößern, finden Sie unter [Festlegen der Größe des Kombinationsfelds und einem Dropdown-Listenfeld](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).

> [!NOTE]
> Win32-Projekte, die mit dieser Prozedur können keine Werte hinzugefügt (die **Daten** Eigenschaft abgeblendet ist, für die Win32-Projekte). Da Win32-Projekte nicht über Bibliotheken, die diese Funktion hinzuzufügen verfügen, müssen Sie Werte an ein Kombinationsfeld mit einem Win32-Projekt programmgesteuert hinzufügen.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>So testen Sie die Darstellung der Werte in einem Kombinationsfeld

1. Nach der Eingabe von Werten in der **Daten** -Eigenschaft, klicken Sie auf die **Test** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

   Versuchen Sie es in den gesamten Wert-Liste nach unten scrollen. Werte angezeigt werden, genau wie die Eingabe in die **Daten** -Eigenschaft in der **Eigenschaften** Fenster. Es gibt keine Rechtschreib- oder Großschreibung zu überprüfen.

   Drücken Sie **ESC-Taste** zum Zurückgeben der **Dialogfeld** Editor.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
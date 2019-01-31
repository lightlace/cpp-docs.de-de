---
title: Anzeigen und Hinzufügen von ActiveX-Steuerelemente in einem Dialogfeld (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
ms.openlocfilehash: 139407ec1d4e1bfad6bb06854dc24b86ce7014e8
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293610"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box-c"></a>Anzeigen und Hinzufügen von ActiveX-Steuerelemente in einem Dialogfeld (C++)

Visual Studio ermöglicht Ihnen das Einfügen von ActiveX-Steuerelementen in Ihr Dialogfeld.

Die **ActiveX-Steuerelement einfügen** Dialogfeld können Sie zum Einfügen von ActiveX-Steuerelemente in einem Dialogfeld bei der Verwendung der [Dialog-Editor](../windows/dialog-editor.md). Dieses Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**ActiveX-Steuerelement**|Zeigt eine Liste von ActiveX-Steuerelementen. Einfügen eines Steuerelements in diesem Dialogfeld ist eine Wrapperklasse nicht generieren. Wenn Sie eine Wrapperklasse benötigen, verwenden Sie [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) erstellen (Weitere Informationen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)). Wenn ein ActiveX-Steuerelement in diesem Dialogfeld nicht angezeigt wird, versuchen Sie es Installieren des Steuerelements entsprechend des Anbieters-Anweisungen.|
|**Pfad**|Zeigt die Datei, die in der das ActiveX-Steuerelement gefunden wird.|

Sie können Steuerelemente im Platzieren der **Toolbox** Fenster für den leichteren Zugriff. Weitere Informationen finden Sie unter [Toolbox](/visualstudio/ide/reference/).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-see-the-activex-controls-you-have-available"></a>So zeigen Sie die verfügbaren ActiveX-Steuerelemente an

1. Öffnen Sie ein Dialogfeld im Dialog-Editor.

1. Mit der rechten Maustaste an einer beliebigen Stelle im Text des Dialogfelds.

1. Wählen Sie im Kontextmenü den Befehl **ActiveX-Steuerelement einfügen**.

   Die **ActiveX-Steuerelement einfügen** Dialogfeld angezeigt wird, stellt alle ActiveX-Steuerelemente auf Ihrem System. Unten im Dialogfeld wird der Pfad der Datei des ActiveX-Steuerelements angezeigt.

## <a name="to-add-an-activex-control-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld ein Active X-Steuerelement hinzu

1. In der **ActiveX-Steuerelement einfügen** Dialogfeld Wählen Sie das gewünschte Steuerelement Ihrem Dialogfeld hinzufügen, und wählen Sie **OK**.

   Das Steuerelement wird im Dialogfeld angezeigt, wo Sie es bearbeiten oder Handler für es erstellen können, ganz wie bei jedem anderen Steuerelement.

   > [!NOTE]
   > Sie können ActiveX-Steuerelemente zum [Toolbox](/visualstudio/ide/reference/toolbox)-Fenster hinzufügen.

   > [!CAUTION]
   > Der Vertrieb ist möglicherweise nicht für alle ActiveX-Steuerelemente auf Ihrem System rechtlich zulässig. Informieren Sie sich im Lizenzvertrag für die Software, die die Steuerelemente installiert hat, oder wenden Sie sich an den Hersteller der Software.

   Sie können Steuerelemente im Platzieren der **Toolbox** Fenster für den leichteren Zugriff. Weitere Informationen finden Sie unter [Toolbox](/visualstudio/ide/reference/toolbox).

## <a name="to-edit-properties-for-an-activex-control"></a>So bearbeiten Sie Eigenschaften für ein ActiveX-Steuerelement

ActiveX-Steuerelemente von unabhängigen Softwareanbietern stammen möglicherweise mit eigenen Eigenschaften und Merkmale. Eigenschaften für ActiveX-Steuerelemente werden angezeigt, der **Eigenschaften** Fenster. Darüber hinaus werden alle von den Schreibern, der das ActiveX-Steuerelement erstellten Eigenschaftenseiten angezeigt, der **Eigenschaftenseiten** (Dialogfeld) (Anzeigen der **Eigenschaftenseite** für ein bestimmtes ActiveX-Steuerelement, klicken Sie auf die  **Eigenschaftenseite** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)).

Auf der Eigenschaftenseite für ein ActiveX-Steuerelement, je nach den Eigenschaftenblättern, die als Teil des ActiveX-Steuerelements enthalten sind, werden verschiedene Registerkarten angezeigt.

> [!NOTE]
> Das folgende Verfahren gilt für die Verwendung von auf der Seite der zum Bearbeiten von ActiveX-Steuerelemente. Sie können auch navigieren und Bearbeiten von ActiveX-Eigenschaften in der neuen **Eigenschaften** Fenster.

1. Wählen Sie die **ActiveX** Steuerelement.

1. Auf der **Ansicht** , wählen Sie im Menü **Eigenschaftenseite** und ihre Eigenschaften anzuzeigen.

1. Nehmen Sie Änderungen an, nach Bedarf auf der Eigenschaftenseite.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)<br/>
[Anzeigen und Hinzufügen von ActiveX-Steuerelementen zu einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)<br/>
[Registerkarte „Dialog-Editor“, „Toolbox“](../windows/dialog-editor-tab-toolbox.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>

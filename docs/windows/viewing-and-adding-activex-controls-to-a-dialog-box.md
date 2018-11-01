---
title: Anzeigen und Hinzufügen von ActiveX-Steuerelemente in einem Dialogfeld (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
ms.openlocfilehash: 947318fb9f628c1184398c039c9697128b09c869
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642506"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box-c"></a>Anzeigen und Hinzufügen von ActiveX-Steuerelemente in einem Dialogfeld (C++)

Visual Studio ermöglicht Ihnen das Einfügen von ActiveX-Steuerelementen in Ihr Dialogfeld.

### <a name="to-see-the-activex-controls-you-have-available"></a>So zeigen Sie die verfügbaren ActiveX-Steuerelemente an

1. Öffnen Sie ein Dialogfeld im Dialog-Editor.

2. Klicken Sie an einer beliebigen Stelle im Körper des Dialogfelds mit der rechten Maustaste.

3. Klicken Sie im Kontextmenü auf **ActiveX-Steuerelement einfügen**.

   Das Dialogfeld [ActiveX-Steuerelement einfügen](../windows/insert-activex-control-dialog-box.md) wird angezeigt und stellt alle ActiveX-Steuerelemente auf dem System dar. Unten im Dialogfeld wird der Pfad der Datei des ActiveX-Steuerelements angezeigt.

### <a name="to-add-an-activex-control-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld ein Active X-Steuerelement hinzu

1. Wählen Sie im Dialogfeld [ActiveX-Steuerelement einfügen](../windows/insert-activex-control-dialog-box.md)das Steuerelement aus, das Sie Ihrem Dialogfeld hinzufügen möchten, und klicken Sie auf **OK**.

   Das Steuerelement wird im Dialogfeld angezeigt, wo Sie es bearbeiten oder Handler für es erstellen können, ganz wie bei jedem anderen Steuerelement.

   > [!NOTE]
   > Sie können ActiveX-Steuerelemente zum [Toolbox](/visualstudio/ide/reference/toolbox)-Fenster hinzufügen.

   > [!CAUTION]
   > Der Vertrieb ist möglicherweise nicht für alle ActiveX-Steuerelemente auf Ihrem System rechtlich zulässig. Informieren Sie sich im Lizenzvertrag für die Software, die die Steuerelemente installiert hat, oder wenden Sie sich an den Hersteller der Software.

   Sie können Steuerelemente im Platzieren der **Toolbox** Fenster für den leichteren Zugriff. Weitere Informationen finden Sie unter [Toolbox](/visualstudio/ide/reference/toolbox).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
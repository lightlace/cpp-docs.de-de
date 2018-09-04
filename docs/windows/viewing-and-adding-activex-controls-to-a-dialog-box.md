---
title: Anzeigen und Hinzufügen von ActiveX-Steuerelemente in einem Dialogfeld | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- Insert ActiveX Control command
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e97393aa6989b7af0a7f3a9a97adaf529f21ba8a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686721"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box"></a>Anzeigen und Hinzufügen von ActiveX-Steuerelementen zu einem Dialogfeld

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

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)  
[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
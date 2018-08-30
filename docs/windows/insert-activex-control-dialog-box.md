---
title: Dialogfeld des ActiveX-Steuerelement einfügen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.insertActiveXControls
dev_langs:
- C++
helpviewer_keywords:
- Insert ActiveX Control dialog box
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0cf6c5efb0c7613c1332ce05483bd311b037a9b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194481"
---
# <a name="insert-activex-control-dialog-box"></a>ActiveX-Steuerelement einfügen (Dialogfeld)

Dieses Dialogfeld können Sie [Einfügen von ActiveX-Steuerelemente in Ihrem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md) bei der Verwendung der [Dialog-Editor](../windows/dialog-editor.md).

### <a name="activex-control"></a>ActiveX-Steuerelement

Zeigt eine Liste von ActiveX-Steuerelementen. Einfügen eines Steuerelements in diesem Dialogfeld ist eine Wrapperklasse nicht generieren. Wenn Sie eine Wrapperklasse benötigen, verwenden Sie [Klassenansicht](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) erstellen (Weitere Informationen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)). Wenn ein ActiveX-Steuerelement in diesem Dialogfeld nicht angezeigt wird, versuchen Sie es Installieren des Steuerelements entsprechend des Anbieters-Anweisungen.

### <a name="path"></a>Pfad

Zeigt die Datei, die in der das ActiveX-Steuerelement gefunden wird.

Sie können Steuerelemente im Platzieren der **Toolbox** Fenster für den leichteren Zugriff. Weitere Informationen finden Sie unter [Dialogfeld Toolbox anpassen](https://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Registerkarte „Dialog-Editor“, „Toolbox“](../windows/dialog-editor-tab-toolbox.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)
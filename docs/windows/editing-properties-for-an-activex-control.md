---
title: Bearbeiten von Eigenschaften für ein ActiveX-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], editing properties
- ActiveX controls [C++], properties
ms.assetid: e5880c62-36c7-4701-bc99-97a82974c22a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e754307c35d10aa36680a42415bd3a5b781321ba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384844"
---
# <a name="editing-properties-for-an-activex-control"></a>Bearbeiten von Eigenschaften für ein ActiveX-Steuerelement

ActiveX-Steuerelemente von unabhängigen Softwareanbietern stammen möglicherweise mit eigenen Eigenschaften und Merkmale. Eigenschaften für ActiveX-Steuerelemente werden angezeigt, der **Eigenschaften** Fenster. Darüber hinaus werden alle von den Schreibern, der das ActiveX-Steuerelement erstellten Eigenschaftenseiten angezeigt, der **Eigenschaftenseiten** (Dialogfeld) (Anzeigen der **Eigenschaftenseite** für ein bestimmtes ActiveX-Steuerelement, klicken Sie auf die  **Eigenschaftenseite** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)).

Auf der Eigenschaftenseite für ein ActiveX-Steuerelement, je nach den Eigenschaftenblättern, die als Teil des ActiveX-Steuerelements enthalten sind, werden verschiedene Registerkarten angezeigt.

> [!NOTE]
> Das folgende Verfahren gilt für die Verwendung von auf der Seite der zum Bearbeiten von ActiveX-Steuerelemente. Sie können auch navigieren und Bearbeiten von ActiveX-Eigenschaften in der neuen **Eigenschaften** Fenster.

### <a name="to-edit-properties-for-an-activex-control"></a>So bearbeiten Sie Eigenschaften für ein ActiveX-Steuerelement

1. Wählen Sie die **ActiveX** Steuerelement.

2. Auf der **Ansicht** Menü klicken Sie auf **Eigenschaftenseite** und ihre Eigenschaften anzuzeigen.

3. Nehmen Sie Änderungen an, nach Bedarf auf der Eigenschaftenseite.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anzeigen und Hinzufügen von ActiveX-Steuerelementen zu einem Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
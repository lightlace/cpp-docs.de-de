---
title: Verwenden eine Windows-Benutzersteuerelement in MFC bilden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/08/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4fef169cb0e2386c1629064ad7ea8a1a70a5c517
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382075"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Verwenden eines Windows Form-Benutzersteuerelements in MFC

Verwenden der MFC-Windows Forms-Unterstützungsklassen, können Sie Windows Forms-Steuerelementen in MFC-Anwendungen als ActiveX-Steuerelement in MFC-Dialogfelder oder Ansichten hosten. Darüber hinaus können Windows Forms-Formulare als MFC-Dialogfelder gehostet werden.

Den folgenden Abschnitten wird beschrieben, wie Sie:

- Hosten eines Windows Forms-Steuerelements in MFC-Dialogfeld.

- Hosten Sie ein Windows Forms-Benutzersteuerelements als MFC-Ansicht.

- Hosten Sie ein Windows Forms-Formular als MFC-Dialogfeld ein.

> [!NOTE]
> MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft (Projekte, in dem `_AFXDLL` definiert ist).

> [!NOTE]
> Bei der Erstellung der Anwendung eine private (geänderte) Kopie der MFC-Windows Forms-Schnittstellen-DLL (mfcmifc80.dll) kann es nicht im GAC zu installieren, es sei denn, Sie den Microsoft-Schlüssel durch Ihren eigenen Anbieter-Schlüssel zu ersetzen. Weitere Informationen zum Signieren der Assembly, finden Sie unter [Programmieren mit Assemblys](/dotnet/framework/app-domains/programming-with-assemblies) und [Assemblys mit starken Namen (Assemblysignierung) (C++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Wenn die MFC-Anwendung Windows Forms verwendet, müssen Sie mfcmifc80.dll mit Ihrer Anwendung verteilen. Weitere Informationen finden Sie unter [Neuverteilen der MFC-Bibliothek](../ide/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Referenz

[CWinFormsControl-Klasse](../mfc/reference/cwinformscontrol-class.md)

[CWinFormsDialog-Klasse](../mfc/reference/cwinformsdialog-class.md)

[CWinFormsView-Klasse](../mfc/reference/cwinformsview-class.md)

[ICommandSource-Schnittstelle](../mfc/reference/icommandsource-interface.md)

[ICommandTarget-Schnittstelle](../mfc/reference/icommandtarget-interface.md)

[ICommandUI-Schnittstelle](../mfc/reference/icommandui-interface.md)

[IView-Schnittstelle](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>Verwandte Abschnitte

[Windows Forms](/dotnet/framework/winforms/index)

[Windows Forms-Steuerelemente](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[Formularansichten](../mfc/form-views-mfc.md)

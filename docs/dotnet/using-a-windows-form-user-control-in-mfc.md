---
title: Mithilfe einer Windows-Benutzersteuerelement in MFC bilden | Microsoft Docs
ms.custom: 
ms.date: 1/08/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a3289509c0cfe6016fcace34c76f145a505ecf3b
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2018
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Verwenden eines Windows Form-Benutzersteuerelements in MFC

Verwenden die MFC-Windows Forms-Unterstützungsklassen, können Sie Windows Forms-Steuerelemente in einer MFC-Anwendung als ActiveX-Steuerelement in MFC-Dialogfelder oder Sichten hosten. Darüber hinaus können Windows Forms-Formulare als MFC-Dialogfelder gehostet werden.

In den folgenden Abschnitten wird beschrieben, wie Sie:

- Hosten eines Windows Forms-Steuerelements in einem MFC-Dialogfeld.

- Hosten Sie ein Windows Forms-Benutzersteuerelements als MFC-Ansicht an.

- Hosten eines Windows Forms-Formulars als MFC-Dialogfeld.

> [!NOTE]
> MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft sind (Projekte, in denen `_AFXDLL` definiert ist).

> [!NOTE]
> Wenn Sie Ihre Anwendung mit einer privaten (geändert) Kopie der MFC-Windows Forms-Schnittstellen-DLL (mfcmifc80.dll) erstellen, kann es nicht im GAC zu installieren, es sei denn, Sie den Microsoft-Schlüssel durch Ihren eigenen Anbieter Schlüssel zu ersetzen. Weitere Informationen zu Signieren von Assemblys, finden Sie unter [Programmieren mit Assemblys](/dotnet/framework/app-domains/programming-with-assemblies) und [Assemblys mit starken Namen (Assembly signieren) (C + c++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Beispielanwendungen, die mithilfe von Windows Forms, finden Sie unter [BirthdayPicker-Beispiel: .NET Framework-Ressourcen mit Windows Forms zeigt](http://msdn.microsoft.com/ac932aed-5502-4667-be29-709bca435317), [-Rechnerbeispiel: Windows Forms-Taschenrechner](http://msdn.microsoft.com/2283b516-3b7e-45f2-80c4-fdcfb366ce25), und [ Scribble-Beispiel: MDI-Zeichenanwendung](http://msdn.microsoft.com/f025da3e-659b-4222-b991-554a1b8b2358).

Eine beispielanwendung, die Windows Forms mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

Wenn die MFC-Anwendung Windows Forms verwendet, müssen Sie mfcmifc80.dll mit der Anwendung verteilen. Weitere Informationen finden Sie unter [Verteilen der MFC-Bibliothek](../ide/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Verweis

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

[Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)  
[Formularansichten](../mfc/form-views-mfc.md)  

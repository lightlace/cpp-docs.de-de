---
title: Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 921e6fac32d37f8976d53d49adab72fb27ab5e99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632218"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld

MFC ein Windows Forms-Steuerelement als eine besondere Art von ActiveX-Steuerelement hostet und kommuniziert mit dem Steuerelement mithilfe von ActiveX-Schnittstellen, Eigenschaften und Methoden der <xref:System.Windows.Forms.Control> Klasse. Es wird empfohlen, dass Sie den .NET Framework-Eigenschaften und Methoden verwenden, um auf das Steuerelement angewendet werden.

Eine beispielanwendung, die Windows Forms, die mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

> [!NOTE]
>  In der aktuellen Version einer `CDialogBar` Objekt kann keine Windows Forms-Steuerelemente hosten.

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[Vorgehensweise: DDX-/DDV-Datenbindung mit Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>Referenz

[CWinFormsControl-Klasse](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog-Klasse](../mfc/reference/cdialog-class.md) &#124; [CWnd-Klasse](../mfc/reference/cwnd-class.md)&#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>Siehe auch

[Verwenden eines Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Unterschiede beim Programmieren mit Windows Forms und MFC](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
---
title: Hosten ein Windows Forms-Benutzersteuerelements als MFC-Ansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b80b3a9d206ef48df1219d60afdc344874d3bab4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374515"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht

MFC verwendet die CWinFormsView-Klasse zum Hosten eines Windows Forms-Benutzersteuerelements in MFC-Ansicht. MFC-Windows Forms-Ansichten sind die ActiveX-Steuerelemente. Das Benutzersteuerelement als untergeordnetes Element der einheitlichen Ansicht gehostet wird, und nimmt den gesamten Clientbereich der einheitlichen Ansicht.

Das Ergebnis ähnelt das Modell, das die [CFormView-Klasse](../mfc/reference/cformview-class.md). Dadurch können Sie die Nutzung von Windows Forms-Designer und der Laufzeit zum Erstellen von umfassender formularbasierte Sichten.

Da MFC-Windows Forms-Ansichten ActiveX-Steuerelemente sind, sie verfügen nicht über die gleiche `hwnd` wie MFC-Ansichten. Sie können keine auch übergeben werden, als Zeiger auf eine [CView](../mfc/reference/cview-class.md) anzeigen. Im Allgemeinen verwenden Sie .NET Framework-Methoden zum Arbeiten mit Windows Forms-Ansichten, und verlassen sich weniger auf Win32.

Eine beispielanwendung, die Windows Forms, die mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Erstellen des Benutzersteuerelements und Hosten der MDI-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[Vorgehensweise: Hinzufügen von Befehlsrouting zum Windows Forms-Steuerelement](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[Vorgehensweise: Aufrufen von Ereignissen und Methoden des Windows Forms-Steuerelements](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>Siehe auch

[Verwenden eines Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
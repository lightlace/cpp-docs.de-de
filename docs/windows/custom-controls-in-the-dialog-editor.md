---
title: Benutzerdefinierte Steuerelemente im Dialog-Editor (C++)
ms.date: 11/04/2016
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
ms.openlocfilehash: c48ad87948037fa843fdc16a016ae23bf139feb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677096"
---
# <a name="custom-controls-in-the-dialog-editor-c"></a>Benutzerdefinierte Steuerelemente im Dialog-Editor (C++)

Der Dialog-Editor können Sie vorhandene "Benutzerdefiniert" oder "User"-Steuerelemente in eine Dialogfeldvorlage.

> [!NOTE]
> Benutzerdefinierte Steuerelemente in diesem Zusammenhang sind nicht zu verwechseln mit ActiveX-Steuerelementen. ActiveX-Steuerelemente wurden benutzerdefinierte OLE-Steuerelemente bezeichnet. Verwechseln Sie nicht auch diese Steuerelemente mit den ownerdrawn-Steuerelementen in Windows.

Diese Funktion dient als die vom Windows-Steuerelemente verwenden zu können. Zur Laufzeit für das Steuerelement eine Fensterklasse (nicht die gleiche als C++-Klasse) zugeordnet ist. Eine allgemeinere Möglichkeit zum Ausführen der gleichen Aufgabe besteht darin Kontrolle, z. B. ein statisches Steuerelement in einem Dialogfeld zu installieren. Klicken Sie dann zur Laufzeit in die [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) funktionieren, entfernen Sie das Steuerelement aus, und durch Ihr eigenes benutzerdefiniertes Steuerelement ersetzen.

Dies ist eine alte Technik. Noch heute in den meisten Fällen sollten Sie ein ActiveX-Steuerelement oder eine Unterklasse eines allgemeinen Steuerelements von Windows zu schreiben.

Für benutzerdefinierte Steuerelemente sind Sie auf:

- Festlegen des Speicherorts im Dialogfeld an.

- Eingeben einer Beschriftung.

- Identifizieren den Namen der Windows-Klasse des Steuerelements (Ihr Anwendungscode muss das Steuerelement mit diesem Namen registrieren).

- Geben einen 32-Bit-Hexadezimalwert, das Format des Steuerelements legt diese fest.

- Wenn den erweiterten Stil.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
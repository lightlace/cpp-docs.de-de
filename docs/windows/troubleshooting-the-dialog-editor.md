---
title: Problembehandlung für den Dialog-Editor (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 21882868-5ac4-4a41-a4a6-eaaa059402ea
ms.openlocfilehash: fe0fe704b5c17d0db4e3419f29d21f0e60bc4211
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484954"
---
# <a name="troubleshooting-the-dialog-editor-c"></a>Problembehandlung für den Dialog-Editor (C++)

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

Im folgenden sind einige Punkte, die davon Sie bedenken sollten bei der Arbeit in C++ **Dialogfeld** Editor:

## <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Hinzufügen von Steuerelementen zu einem Dialogfeld bewirkt, dass das Dialogfeld nicht mehr funktioniert

Nach dem Hinzufügen einer allgemeinen Steuerelements oder rich-Edit-Steuerelement in einem Dialogfeld an, nicht es angezeigt, wenn Sie Sie das Dialogfeld Testen oder das Dialogfeld selbst wird nicht angezeigt.

### <a name="example-of-the-problem"></a>Beispiel für das problem

1. Erstellen Sie eine Win32-Projekts, das die Anwendungseinstellungen ändern, damit Sie eine Windows-Anwendung (keine Konsolen-app erstellen).

1. In [Ressourcenansicht](../windows/resource-view-window.md), doppelklicken Sie auf die RC-Datei.

1. Doppelklicken Sie unter der Dialogfeldoption auf die **zu** Feld.

1. Hinzufügen einer **IP-Adressensteuerelement** auf das Dialogfeld.

1. Speichern und **alles neu erstellen**.

1. Führen Sie das Programm an.

1. In des Dialogfelds **helfen** im Menü klicken Sie auf die **zu** Befehl, kein Dialogfeld angezeigt wird.

### <a name="the-cause"></a>Die Ursache

Derzeit den **Dialogfeld** Editor nicht Code automatisch zu Ihrem Projekt hinzugefügt werden, wenn Drag & drop die folgenden allgemeinen Steuerelemente oder Rich--Steuerelemente in einem Dialogfeld Edit. Auch Visual Studio bietet Fehler oder Warnung, wenn dieses Problem auftritt. Um das Problem zu beheben, fügen Sie den Code für das Steuerelement manuell hinzu.

||||
|-|-|-|
|Schiebereglersteuerung|Strukturansicht-Steuerelement|Datums-/Zeitauswahl|
|Drehfeld-Steuerelement|Registerkarten-Steuerelement|Monatskalender|
|Statuskontrolle|Animation-Steuerelement|IP-Adressensteuerelement|
|Abkürzungstaste|Rich Edit-Steuerelements|Erweitertes Kombinationsfeld|
|Listensteuerelement|Rich Edit 2.0-Steuerelements|Benutzerdefiniertes Steuerelement|

### <a name="fix-for-common-controls"></a>Korrektur für allgemeine Steuerelemente

Um allgemeine Steuerelemente in einem Dialogfeld verwenden zu können, müssen Sie zum Aufrufen [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) oder `AFXInitCommonControls` vor der Erstellung des Dialogfelds.

### <a name="fix-for-richedit-controls"></a>Korrektur für RichEdit-Steuerelemente

Rufen Sie `LoadLibrary` für Rich--Steuerelemente Edit. Weitere Informationen finden Sie unter [über Rich-Edit-Steuerelemente](/windows/desktop/Controls/about-rich-edit-controls) im Windows SDK und [Überblick über das RichEdit-Steuerelement](../mfc/overview-of-the-rich-edit-control.md).

### <a name="requirements"></a>Anforderungen

Win32

## <a name="using-the-richedit-10-control-with-mfc"></a>Verwenden des RichEdit 1.0-Steuerelements mit MFC

Um ein RichEdit-Steuerelement zu verwenden, müssen Sie zuerst Aufrufen [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) beim Laden des RichEdit-2.0-Steuerelements (RICHED20. DLL), oder rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) beim Laden des älteren RichEdit 1.0-Steuerelements (RICHED32. (DLL).

Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber `CRichEditCtrl` dient nur zur Unterstützung des RichEdit-2.0-Steuerelements. Da RichEdit 1.0 und 2.0 des RichEdit ähnlich sind, funktionieren die meisten Methoden. Beachten Sie jedoch, dass es gibt einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise nicht ordnungsgemäß oder überhaupt nicht funktionsfähig.

### <a name="requirements"></a>Anforderungen

MFC

## <a name="see-also"></a>Siehe auch

[Dialog-Editor](../windows/dialog-editor.md)
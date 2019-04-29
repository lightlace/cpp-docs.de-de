---
title: Verwenden von Rückruffeldern in einem Steuerelement für die Datums- und Zeitauswahl
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 874f73df3dda3a720d4346ae3fb0136c662221db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403580"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Verwenden von Rückruffeldern in einem Steuerelement für die Datums- und Zeitauswahl

Zusätzlich zu der standardmäßigen Zeichen, die Datums- / Zeitauswahl-Felder definieren, können Sie die Ausgabe anpassen, indem Sie bestimmte Teile einer benutzerdefinierten Formatzeichenfolge als Rückruffeldern angeben. Um eine Callback-Feld zu deklarieren, enthalten Sie ein oder mehrere "X"-Zeichen (ASCII-Code 88) an einer beliebigen Stelle im Text der Formatzeichenfolge. Z. B. die folgende Zeichenfolge "" heutzutage ist: 'Yy' / 'MM' / 'Dd' (Tag 'X')'"bewirkt, dass die Datums- / Zeitauswahl-Steuerelement, um den aktuellen Wert als das Jahr, gefolgt von den Monat, Datum und den Tag des Jahres anzuzeigen.

> [!NOTE]
>  Die Anzahl von x in einem Rückruf Feld entspricht nicht der Anzahl von Zeichen, die angezeigt werden.

Sie können zwischen mehreren Rückruffelder in eine benutzerdefinierte Zeichenfolge, indem Sie das Zeichen "X" Wiederholen unterscheiden. Daher die Formatzeichenfolge "XXddddMMMdd', ' YyyXXX" enthält zwei Rückruffelder "XX" und "XXX".

> [!NOTE]
>  Rückruffelder werden als gültigen Felder behandelt, damit Ihre Anwendung vorbereitet werden muss, um DTN_WMKEYDOWN benachrichtigungsmeldungen zu verarbeiten.

Implementieren von Rückruffeldern in Ihrer Datums- / Zeitauswahl-Steuerelement besteht aus drei Teilen:

- Initialisieren die benutzerdefinierte Formatzeichenfolge

- Behandeln der DTN_FORMATQUERY-Benachrichtigung

- Behandeln von DTN_FORMAT-Benachrichtigung

## <a name="initializing-the-custom-format-string"></a>Initialisieren die benutzerdefinierte Formatzeichenfolge

Initialisieren Sie die benutzerdefinierte Zeichenfolge mit einem Aufruf von `CDateTimeCtrl::SetFormat`. Weitere Informationen finden Sie unter [mithilfe von benutzerdefinierten Formatzeichenfolgen in einem Datums- und Zeitauswahl-Steuerelement](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Allgemeine Ort, an die benutzerdefinierte Formatzeichenfolge festgelegt ist, in der `OnInitDialog` Funktion der enthaltenden Dialogfeldklasse oder `OnInitialUpdate` Funktion der enthaltenden Klasse anzeigen.

## <a name="handling-the-dtnformatquery-notification"></a>Behandeln der DTN_FORMATQUERY-Benachrichtigung

Wenn das Steuerelement die Formatzeichenfolge analysiert und Rückruffeld auftritt, sendet die Anwendung DTN_FORMAT und DTN_FORMATQUERY benachrichtigungsmeldungen an. Die Rückruf-Feld-Zeichenfolge ist in die Benachrichtigungen enthalten, sodass Sie ermitteln können, welche Rückruffeld abgefragt wird.

DTN_FORMATQUERY-Benachrichtigung wird gesendet, um die maximal zulässige Größe in Pixel der Zeichenfolge abzurufen, die im aktuellen Rückruffeld angezeigt wird.

Um diesen Wert ordnungsgemäß zu berechnen, müssen Sie die Höhe und Breite der Zeichenfolge, die für das Feld ersetzen sollen berechnen verwenden die Schriftart des Steuerelements angezeigt. Die Berechnung der Zeichenfolge erfolgt einfach durch einen Aufruf der [GetTextExtentPoint32](/windows/desktop/api/wingdi/nf-wingdi-gettextextentpoint32a) Win32-Funktion. Nachdem die Größe ermittelt wurde, übergeben Sie den Wert an die Anwendung, und beenden Sie die Handler-Funktion.

Im folgende Beispiel wird eine Methode zum Angeben der Größe der Rückrufzeichenfolge:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

Sobald die Größe des aktuellen Rückruffeld berechnet wurde, müssen Sie einen Wert für das Feld angeben. Dies erfolgt im Ereignishandler für die DTN_FORMAT-Benachrichtigung.

## <a name="handling-the-dtnformat-notification"></a>Behandeln von DTN_FORMAT-Benachrichtigung

DTN_FORMAT-Benachrichtigung wird von der Anwendung verwendet, um die Zeichenfolge anzufordern, die ersetzt wird. Das folgende Beispiel zeigt eine mögliche Methode:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  Der Zeiger auf die **NMDATETIMEFORMAT** Struktur wird ermittelt, indem Sie den ersten Parameter die Benachrichtigungshandler in den richtigen Typ umwandeln.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

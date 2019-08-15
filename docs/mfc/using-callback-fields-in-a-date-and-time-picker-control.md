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
ms.openlocfilehash: 5d08c349253e62c15553cfa0452cee930b1a1876
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513507"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Verwenden von Rückruffeldern in einem Steuerelement für die Datums- und Zeitauswahl

Zusätzlich zu den Standard Formatierungszeichen, die Felder für Datums-und Zeitauswahl definieren, können Sie die Ausgabe anpassen, indem Sie bestimmte Teile einer benutzerdefinierten Format Zeichenfolge als Rückruf Felder angeben. Um ein Rückruf Feld zu deklarieren, fügen Sie ein oder mehrere "X"-Zeichen (ASCII-Code 88) an beliebiger Stelle im Text der Format Zeichenfolge ein. Die folgende Zeichenfolge "" ist heute beispielsweise "yy"/"mm"/"dd" (Tag "X") ", bewirkt, dass das Steuerelement für die Datums-und Uhrzeit Auswahl den aktuellen Wert als das Jahr anzeigt, auf das der Monat, das Datum und schließlich der Tag des Jahres folgt.

> [!NOTE]
>  Die Anzahl der X-Werte in einem Rückruf Feld entspricht nicht der Anzahl der Zeichen, die angezeigt werden.

Sie können zwischen mehreren Rückruf Feldern in einer benutzerdefinierten Zeichenfolge unterscheiden, indem Sie das "X"-Zeichen wiederholen. Daher enthält die Format Zeichenfolge "XXddddMMMdd", "yyyXXX" zwei eindeutige Rückruf Felder: "XX" und "xxx".

> [!NOTE]
>  Rückruf Felder werden als gültige Felder behandelt, sodass Ihre Anwendung für die Verarbeitung von DTN_WMKEYDOWN-Benachrichtigungs Meldungen vorbereitet werden muss.

Das Implementieren von Rückruf Feldern in einem Steuerelement für die Datums-und Uhrzeit Auswahl besteht aus drei Teilen:

- Initialisieren der benutzerdefinierten Format Zeichenfolge

- Behandeln der DTN_FORMATQUERY-Benachrichtigung

- Behandeln der DTN_FORMAT-Benachrichtigung

## <a name="initializing-the-custom-format-string"></a>Initialisieren der benutzerdefinierten Format Zeichenfolge

Initialisieren Sie `CDateTimeCtrl::SetFormat`die benutzerdefinierte Zeichenfolge mit einem-Befehl. Weitere Informationen finden Sie unter [Verwenden von benutzerdefinierten Format Zeichenfolgen in einem Steuerelement für Datums-und Zeit](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)Auswahl. Die benutzerdefinierte Format Zeichenfolge kann in der `OnInitDialog` Funktion der enthaltenden Dialogfeld Klasse oder `OnInitialUpdate` Funktion der enthaltenden Ansichts Klasse festgelegt werden.

## <a name="handling-the-dtn_formatquery-notification"></a>Behandeln der DTN_FORMATQUERY-Benachrichtigung

Wenn das Steuerelement die Format Zeichenfolge analysiert und ein Rückruf Feld findet, sendet die Anwendung DTN_FORMAT-und DTN_FORMATQUERY-Benachrichtigungs Meldungen. Die Rückruf Feld Zeichenfolge ist in den Benachrichtigungen enthalten, sodass Sie bestimmen können, welches Rückruf Feld abgefragt wird.

Die DTN_FORMATQUERY-Benachrichtigung wird gesendet, um die maximal zulässige Größe in Pixel der Zeichenfolge abzurufen, die im aktuellen Rückruf Feld angezeigt wird.

Zum ordnungsgemäßen berechnen dieses Werts müssen Sie die Höhe und Breite der Zeichenfolge berechnen, um das Feld zu ersetzen, indem Sie die Anzeige Schriftart des Steuer Elements verwenden. Die tatsächliche Berechnung der Zeichenfolge lässt sich problemlos durch einen aufzurufenden [GetTextExtentPoint32](/windows/win32/api/wingdi/nf-wingdi-gettextextentpoint32w) Win32-Funktion erreichen. Nachdem die Größe bestimmt wurde, übergeben Sie den Wert zurück an die Anwendung, und beenden Sie die Handlerfunktion.

Im folgenden Beispiel wird eine Methode zum Bereitstellen der Größe der Rückruf Zeichenfolge veranschaulicht:

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

Nachdem die Größe des aktuellen Rückruf Felds berechnet wurde, müssen Sie einen Wert für das Feld angeben. Dies erfolgt im Handler für die DTN_FORMAT-Benachrichtigung.

## <a name="handling-the-dtn_format-notification"></a>Behandeln der DTN_FORMAT-Benachrichtigung

Die DTN_FORMAT-Benachrichtigung wird von der Anwendung verwendet, um die Zeichenfolge anzufordern, die ersetzt wird. Im folgenden Beispiel wird eine mögliche Methode veranschaulicht:

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  Der Zeiger auf die **NMDATETIMEFORMAT** -Struktur wird gefunden, indem der erste Parameter des Benachrichtigungs Handlers in den richtigen Typ umgewandelt wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

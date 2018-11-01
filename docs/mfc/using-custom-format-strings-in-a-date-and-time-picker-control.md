---
title: Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement für die Datums- und Zeitauswahl
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 2e3e980649264a6842abcc9491171e5105dbab17
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557494"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement für die Datums- und Zeitauswahl

Standardmäßig enthalten Picker-Steuerelemente für Datum und Uhrzeit an, dass die drei Typen (jedes Format für ein eindeutiges Format) für die Anzeige von, das aktuelle Datum oder Uhrzeit zu formatieren:

- **DTS_LONGDATEFORMAT** zeigt das Datum im langen Format erzeugt die Ausgabe sieht etwa wie "Mittwoch, 3. Januar 2000".

- **DTS_SHORTDATEFORMAT** zeigt das Datum im kurzen Format, die Ausgabe sieht etwa wie "1/3/00" erzeugt.

- **DTS_TIMEFORMAT** zeigt die Uhrzeit im langen Format erzeugt die Ausgabe sieht etwa wie "5:31:42 PM".

Allerdings können Sie die Darstellung von Datum und Uhrzeit anpassen, mit der eine benutzerdefinierte Formatzeichenfolge. Diese benutzerdefinierte Zeichenfolge besteht aus entweder vorhandene Formatzeichen, Nonformat Zeichen oder eine Kombination aus beidem. Nachdem die benutzerdefinierte Zeichenfolge erstellt wurde, stellen Sie einen Aufruf von [CDateTimeCtrl:: setFormat initialisiert](../mfc/reference/cdatetimectrl-class.md#setformat) in die benutzerdefinierte Zeichenfolge übergeben. Die Datums- / Zeitauswahl-Steuerelement werden den aktuellen Wert, der mit Ihrer benutzerdefinierten Formatzeichenfolge angezeigt.

Der folgende Beispielcode (wo *M_dtPicker* ist der `CDateTimeCtrl` Objekt) veranschaulicht eine mögliche Lösung:

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

Zusätzlich zu benutzerdefinierten Formatzeichenfolgen Datums- / Zeitauswahl steuert außerdem die Unterstützung [Rückruffeldern](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


---
title: Verwenden von Rückruffeldern in einem Datums- und Zeitauswahl Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b0d59aa8c30e9308448467bb198e898106e61f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383785"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>Verwenden von Rückruffeldern in einem Steuerelement für die Datums- und Zeitauswahl
Zusätzlich zu den standardmäßigen Formatierungszeichen, die Datums- und Zeitauswahl Uhrzeitfelder zu definieren, können Sie Ihre Ausgabe anpassen, indem Sie bestimmte Teile der eine benutzerdefinierte Formatzeichenfolge als Rückruffeldern angeben. Um einen Rückruffeld nicht deklariert werden, enthalten Sie ein oder mehrere "X"-Zeichen (ASCII-Code 88) an einer beliebigen Stelle im Text der Formatzeichenfolge. Z. B. die folgende Zeichenfolge "" ist: 'Yy' / 'MM' / 'Dd' (Tag 'X')'"bewirkt, dass das Datum und Uhrzeit Kontoauswahl-Steuerelement zur Anzeige des aktuellen Werts als Jahr, Monat, Datum und schließlich den Tag des Jahres gefolgt.  
  
> [!NOTE]
>  Die Anzahl der x in einem Rückruf Feld entspricht die Anzahl der Zeichen, die angezeigt werden sollen.  
  
 Sie können mehrere Rückruffeldern in einer benutzerdefinierten Zeichenfolge durch die Wiederholung des Zeichens "X" unterscheiden. Daher die Formatzeichenfolge "XXddddMMMdd", "YyyXXX" enthält zwei Rückruffelder "XX" und "XXX".  
  
> [!NOTE]
>  Rückruffelder als gültige Felder behandelt werden, damit Ihre Anwendung vorbereitet sein muss, behandeln **DTN_WMKEYDOWN** benachrichtigungsmeldungen.  
  
 Implementieren von Rückruffeldern in Ihre Datums- / Zeitauswahl-Steuerelement besteht aus drei Teilen:  
  
-   Initialisieren die benutzerdefinierte Formatzeichenfolge  
  
-   Behandlung von der **DTN_FORMATQUERY** Benachrichtigung  
  
-   Behandlung von der **DTN_FORMAT** Benachrichtigung  
  
## <a name="initializing-the-custom-format-string"></a>Initialisieren die benutzerdefinierte Formatzeichenfolge  
 Initialisieren Sie die benutzerdefinierte Zeichenfolge mit einem Aufruf von `CDateTimeCtrl::SetFormat`. Weitere Informationen finden Sie unter [mithilfe von benutzerdefinierten Formatzeichenfolgen in einem Datum und Uhrzeit die Datumsauswahl](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md). Die benutzerdefinierte Formatzeichenfolge festzulegende wird häufig der `OnInitDialog` Funktion der enthaltenden Dialogfeldklasse oder `OnInitialUpdate` Funktion der enthaltenden Ansichtsklasse.  
  
## <a name="handling-the-dtnformatquery-notification"></a>Behandeln der DTN_FORMATQUERY-Benachrichtigung  
 Wenn das Steuerelement die Formatzeichenfolge analysiert und eine Rückruffeld trifft, um die Anwendung sendet **DTN_FORMAT** und **DTN_FORMATQUERY** benachrichtigungsmeldungen. Die Rückruf-Feld-Zeichenfolge ist mit der Benachrichtigungen enthalten, sodass Sie ermitteln können, welches Rückruffeld abgefragt wird.  
  
 Die **DTN_FORMATQUERY** Benachrichtigung wird gesendet, um die maximal zulässige Größe in Pixel der Zeichenfolge abzurufen, die in der aktuellen Rückruffeld angezeigt werden.  
  
 Um diesen Wert ordnungsgemäß zu berechnen, müssen die Höhe und Breite der Zeichenfolge, die für das Feld ersetzen sollen berechnen mithilfe des Bildschirm-Schriftart des Steuerelements. Die eigentliche Berechnung der Zeichenfolge erfolgt einfach durch Aufrufen der [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) Win32-Funktion. Nachdem Sie die Größe ermittelt haben, übergeben Sie den Wert an die Anwendung und beenden Sie die Handlerfunktion zu.  
  
 Im folgende Beispiel wird eine Methode zum Angeben der Größe der Rückrufzeichenfolge:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 Sobald die Größe des aktuellen Rückruf Felds berechnet wurde, müssen Sie einen Wert für das Feld angeben. Dies erfolgt im Handler für das **DTN_FORMAT** Benachrichtigung.  
  
## <a name="handling-the-dtnformat-notification"></a>Behandeln von DTN_FORMAT-Benachrichtigung  
 Die **DTN_FORMAT** Benachrichtigung wird von der Anwendung verwendet, um die Zeichenfolge anzufordern, die ersetzt wird. Im folgende Beispiel wird eine mögliche Methode veranschaulicht:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  Der Zeiger auf die **NMDATETIMEFORMAT** Struktur wird ermittelt, indem Sie den ersten Parameter der Benachrichtigungshandler, an den richtigen Typ umwandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


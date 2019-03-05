---
title: Handler für Windows-Standardmeldungen
ms.date: 11/04/2016
f1_keywords:
- afx_msg
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
ms.openlocfilehash: d60ae52225ddd993c1768d0b5ce1989ab0192e45
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275388"
---
# <a name="handlers-for-standard-windows-messages"></a>Handler für Windows-Standardmeldungen

Standard-Handler für standard-Windows-Meldungen (**WM_**) sind in der Klasse vordefiniert `CWnd`. Die Klassenbibliothek Basen Namen für diese Handler auf den Nachrichtennamen. Z. B. den Handler für die **WM_PAINT** Nachricht im deklarierten `CWnd` als:

`afx_msg void OnPaint();`

Die **Afx_msg** Schlüsselwort schlägt vor, die Auswirkungen der C++- **virtuellen** Schlüsselwort durch die Handler von anderen unterscheiden `CWnd` Memberfunktionen. Beachten Sie jedoch, dass diese Funktionen nicht virtuelle sind. Sie werden stattdessen über meldungszuordnungen implementiert. Meldungszuordnungen hängt ausschließlich standard Präprozessormakros und nicht für alle Erweiterungen der Programmiersprache C++. Die **Afx_msg** Schlüsselwort in Leerzeichen aufgelöst wird, nach der vorverarbeitung.

Um einen Handler, der definiert, die in einer Basisklasse zu überschreiben, definieren Sie einfach eine Funktion mit den gleichen Prototyp, in der abgeleiteten Klasse und einen meldungszuordnung Eintrag für den Ereignishandler. Der Handler überschreibt"" ein Handler mit dem gleichen Namen in einer der Basisklassen Ihrer Klasse fest.

In einigen Fällen sollte der Handler den außer Kraft gesetzte Handler in der Basisklasse aufrufen, damit der Basisklasse(n) und Windows für die Nachricht ausgeführt werden können. In dem Sie den Handler für die Basisklasse in der Überschreibung aufrufen, hängt von den Umständen ab. Manchmal müssen Sie rufen den Handler für die Basisklasse zuerst und zuletzt manchmal. Manchmal rufen Sie die Basisklassenhandler bedingt, wenn Sie nicht die Meldung zu behandeln. Manchmal sollten Sie den Handler der Basisklasse aufrufen und dann Ihre eigenen Handlercode, je nach Wert oder Zustand, die von der Basisklasse Handler zurückgegebene bedingt auszuführen.

> [!CAUTION]
>  Es ist nicht sicher ist, ändern die Argumente, die an einen Ereignishandler übergeben werden, wenn Sie beabsichtigen, die sie auf einen Basisklassen-Handler übergeben. Z. B. möglicherweise versucht, das Ändern der *nChar* Argument der `OnChar` Handler (in Großbuchstaben umzuwandelnde, z. B.). Dieses Verhalten ist recht undurchsichtig, aber wenn Sie diesen Effekt erzielen, durchführen müssen, verwenden die `CWnd` Memberfunktion `SendMessage` stattdessen.

Wie bestimmt der richtige Weg, um eine bestimmte Nachricht zu überschreiben, wenn das Fenster "Eigenschaften" das Gerüst der Handlerfunktion für eine bestimmte Nachricht schreibt – ein `OnCreate` Handler für **WM_CREATE**, z. B. – es in Form von Skizzen die empfohlene überschriebenen Member-Funktion. Im folgende Beispiel empfiehlt, dass der Handler zuerst den Handler der Basisklasse aufrufen, und fahren Sie fort, nur, wenn kein-1 zurückgegeben wird.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Gemäß der Konvention beginnen die Namen dieser Handler mit dem Präfix "On". Einige dieser Handler akzeptieren keine Argumente, während die anderen mehrere verwendet werden. Einige haben auch einen Rückgabetyp als **"void"**. Die Standardhandler für alle **WM_** Nachrichten werden in dokumentiert die *MFC-Referenz* als Memberfunktionen der Klasse `CWnd` , deren Namen beginnen mit "On". In den memberfunktionsdeklarationen `CWnd` vorangestellt **Afx_msg**.

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)

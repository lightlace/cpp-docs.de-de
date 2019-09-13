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
ms.openlocfilehash: 4f512c3b9a7fce5cddd582fa774742d2b1ac0967
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907428"
---
# <a name="handlers-for-standard-windows-messages"></a>Handler für Windows-Standardmeldungen

Standard Handler für standardmäßige Windows-Meldungen (**WM_** ) sind in der `CWnd`-Klasse vordefiniert. Die Klassen Bibliotheks Basis Namen für diese Handler für den Nachrichten Namen. Der Handler für die **WM_PAINT** -Nachricht wird z. b. `CWnd` in wie folgt deklariert:

`afx_msg void OnPaint();`

Das **afx_msg** -Schlüsselwort schlägt die Auswirkung C++ des **virtuellen** Schlüssel Worts vor, indem die Handler `CWnd` von anderen Element Funktionen unterschieden werden. Beachten Sie jedoch, dass diese Funktionen nicht virtuell sind. Sie werden stattdessen über Nachrichten Zuordnungen implementiert. Meldungs Zuordnungen hängen ausschließlich von standardpräprozessormakros und nicht von C++ Erweiterungen der Sprache ab. Das **afx_msg** -Schlüsselwort wird nach der Vorverarbeitung in Leerraum aufgelöst.

Um einen in einer Basisklasse definierten Handler zu überschreiben, definieren Sie einfach eine Funktion mit dem gleichen Prototyp in der abgeleiteten Klasse, und erstellen Sie einen Meldungs Zuordnungs Eintrag für den Handler. Der Handler "überschreibt" alle Handler desselben Namens in den Basisklassen der Klasse.

In einigen Fällen sollte der Handler den überschriebenen Handler in der Basisklasse aufzurufen, damit die Basisklasse (es) und Windows mit der Nachricht arbeiten können. Wo Sie den Basisklassen Handler in ihrer außer Kraft Setzung aufzurufen, hängt von den Umständen ab. In manchen Fällen müssen Sie zuerst den Basisklassen Handler und manchmal den letzten aufgerufen haben. Manchmal wird der Basisklassen Handler bedingt aufgerufen, wenn Sie sich entscheiden, die Nachricht selbst nicht zu verarbeiten. Manchmal sollten Sie den Basisklassen Handler und dann bedingt ihren eigenen Handlercode ausführen, abhängig von dem Wert oder Zustand, der vom Basisklassen Handler zurückgegeben wird.

> [!CAUTION]
>  Es ist nicht sicher, die an einen Handler übergebenen Argumente zu ändern, wenn Sie beabsichtigen, Sie an einen Basisklassen Handler zu übergeben. Beispielsweise ist es möglicherweise verlockend, das *NCHAR* -Argument des `OnChar` Handlers zu ändern (z. b. zum Konvertieren in Großbuchstaben). Dieses Verhalten ist recht undurchsichtig, aber wenn Sie diesen Effekt erreichen müssen, verwenden Sie stattdessen `CWnd` die Member `SendMessage` -Funktion.

Wie bestimmen Sie die ordnungsgemäße Methode zum Überschreiben einer bestimmten Nachricht, wenn der [Klassen-Assistent](reference/mfc-class-wizard.md) das Gerüst der Handlerfunktion für eine bestimmte Nachricht `OnCreate` schreibt – ein Handler für **WM_CREATE**, z. b. – er wird in Form des empfohlenen überschriebene Member-Funktion. Im folgenden Beispiel wird empfohlen, dass der Handler zuerst den Basisklassen Handler aufruft und nur unter der Bedingung fort fährt, dass er-1 nicht zurückgibt.

[!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]

Gemäß der Konvention beginnen die Namen dieser Handler mit dem Präfix "on". Einige dieser Handler akzeptieren keine Argumente, während andere verschiedene Argumente annehmen. Einige haben auch einen anderen Rückgabetyp als **void**. Die Standard Handler für alle **WM_** -Nachrichten werden in der *MFC-Referenz* als Element Funktionen der `CWnd` Klasse dokumentiert, deren Namen mit "on" beginnen. Die Member-Funktions Deklarationen in `CWnd` haben das Präfix **afx_msg**.

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)

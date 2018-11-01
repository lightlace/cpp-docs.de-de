---
title: Vordefinierte Zugriffstasten (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 9ee884123bfe440e2246b6313ba1e37c0b01b494
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541621"
---
# <a name="predefined-accelerator-keys-c"></a>Vordefinierte Zugriffstasten (C++)

Es gibt eine Anzahl vordefinierter Zugriffstasten, die Teil eines Windows-Anwendungsprojekts sein können. Einige dieser virtuellen Tasten sind für die Windows-Umgebung. Andere unterstützen Browser oder Unicode-Anwendungen. Dieser Tasten können in beliebigen Zugriffstasten verwendet werden.

|Key|Beschreibung|
|---------|-----------------|
|VK_ACCEPT|IME akzeptieren|
|VK_BROWSER_BACK|Windows: Zurück-Taste des Browsers|
|VK_BROWSER_FAVORITES|Windows: Favoriten-Taste des Browsers|
|VK_BROWSER_FORWARD|Windows: Vorwärts-Taste des Browsers|
|VK_BROWSER_HOME|Windows: Start- und POS1-Taste des Browsers|
|VK_BROWSER_REFRESH|Windows: Aktualisieren-Taste des Browsers|
|VK_BROWSER_SEARCH|Windows: Such-Taste des Browsers|
|VK_BROWSER_STOP|Windows: Abbrechen-Taste des Browsers|
|VK_CONVERT|IME konvertieren|
|VK_FINAL|IME-Final-Modus|
|VK_HANGUEL|IME-Hanguel-Modus (aus Kompatibilitätsgründen beibehalten; verwenden Sie VK_HANGUL)|
|VK_HANGUL|IME-Hangul-Modus|
|VK_HANJA|IME-Hanja-Modus|
|VK_JUNJA|IME-Junja-Modus|
|VK_KANA|IME-Kana-Modus|
|VK_KANJI|IME-Kanji-Modus|
|VK_LAUNCH_APP1|Windows: Taste für Anwendung 1 starten|
|VK_LAUNCH_APP2|Windows: Taste für Anwendung 2 starten|
|VK_LAUNCH_MAIL|Windows: Taste für E-Mail starten|
|VK_LAUNCH_MEDIA_SELECT|Windows: Taste für Medien auswählen|
|VK_LCONTROL|Linke STRG-Taste|
|VK_LMENU|Linke Menütaste|
|VK_LSHIFT|Linke UMSCHALTTASTE|
|VK_MEDIA_NEXT_TRACK|Windows: Taste für nächsten Titel|
|VK_MEDIA_PLAY_PAUSE|Windows: Taste für Abspielen/Anhalten von Medien|
|VK_MEDIA_PREV_TRACK|Windows: Taste für vorherigen Titel|
|VK_MEDIA_STOP|Windows: Taste für Beenden von Medien|
|VK_MODECHANGE|IME-Modusänderungsanforderung|
|VK_NONCONVERT|IME-Nicht-Konvertierung|
|VK_OEM_1|Windows: für US-Standardtastatur die „;:“-Taste|
|VK_OEM_102|Windows: entweder Taste für spitze Klammer oder für umgekehrten Schrägstrich auf der RT-102-Tasten-Tastatur|
|VK_OEM_2|Windows: für die US-Standardtastatur die "/?" Key|
|VK_OEM_3|Windows: für US-Standardtastatur die „`~“-Taste|
|VK_OEM_4|Windows: für US-Standardtastatur die „[{“-Taste|
|VK_OEM_5|Windows: für die US-Standardtastatur die "\\&#124;' Schlüssel|
|VK_OEM_6|Windows: für US-Standardtastatur die „]}“-Taste|
|VK_OEM_7|Windows: für US-Standardtastatur die „einfache/doppelte Anführungszeichen“-Taste|
|VK_OEM_COMMA|Windows: für alle Länder/Regionen die „,“-Taste|
|VK_OEM_MINUS|Windows: für alle Länder/Regionen die „-“-Taste|
|VK_OEM_PERIOD|Windows: für alle Länder/Regionen die „.“-Taste|
|VK_OEM_PLUS|Windows: für alle Länder/Regionen die „+“-Taste|
|VK_PACKET|Windows: zum Übergeben von Unicode-Zeichen, als handele es sich um Tastatureingaben.|
|VK_RCONTROL|Rechte STRG-Taste|
|VK_RMENU|Rechte Menütaste|
|VK_RSHIFT|Rechte UMSCHALTTASTE|
|VK_SLEEP|Taste für Standbymodus|
|VK_VOLUME_DOWN|Windows: Taste zum Verringern der Lautstärke|
|VK_VOLUME_MUTE|Windows: Taste zum Stummschalten|
|VK_VOLUME_UP|Windows: Taste zum Erhöhen der Lautstärke|
|VK_XBUTTON1|Windows: X1-Maustaste|
|VK_XBUTTON2|Windows: X2-Maustaste|

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zugriffstasten-Editor](../windows/accelerator-editor.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)
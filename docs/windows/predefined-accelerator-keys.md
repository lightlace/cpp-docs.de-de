---
title: Zugriffstasten (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 1e87d80b8995760eecda34334dab702480bd9669
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232122"
---
# <a name="accelerator-keys-c"></a>Zugriffstasten (C++)

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="predefined-accelerator-keys"></a>Vordefinierte Zugriffstasten

Es gibt eine Anzahl vordefinierter Zugriffstasten, die Teil eines Windows-Anwendungsprojekts sein können. Einige dieser virtuellen Tasten sind für die Windows-Umgebung. Andere unterstützen Browser oder Unicode-Anwendungen. Dieser Tasten können in beliebigen Zugriffstasten verwendet werden.

|Key|Beschreibung|
|---------|-----------------|
|VK_ACCEPT|IME akzeptieren|
|VK_BROWSER_BACK|Windows: Browser-zurück-Taste|
|VK_BROWSER_FAVORITES|Windows: Browser-Favoriten-Taste|
|VK_BROWSER_FORWARD|Windows: Browser-vorwärts-Taste|
|VK_BROWSER_HOME|Windows: Browser Start- und POS1-Taste|
|VK_BROWSER_REFRESH|Windows: Browser-aktualisieren-Taste|
|VK_BROWSER_SEARCH|Windows: Browser-suchen-Taste|
|VK_BROWSER_STOP|Windows: Browser-Abbrechen-Taste|
|VK_CONVERT|IME konvertieren|
|VK_FINAL|IME-Final-Modus|
|VK_HANGUEL|IME-Hanguel-Modus (aus Kompatibilitätsgründen beibehalten; verwenden Sie VK_HANGUL)|
|VK_HANGUL|IME-Hangul-Modus|
|VK_HANJA|IME-Hanja-Modus|
|VK_JUNJA|IME-Junja-Modus|
|VK_KANA|IME-Kana-Modus|
|VK_KANJI|IME-Kanji-Modus|
|VK_LAUNCH_APP1|Windows: ANWENDUNGSSTARTTASTE 1 starten|
|VK_LAUNCH_APP2|Windows: ANWENDUNGSSTARTTASTE 2 starten|
|VK_LAUNCH_MAIL|Windows: Starten Sie die Taste für E-Mail|
|VK_LAUNCH_MEDIA_SELECT|Windows: Taste für Medien auswählen|
|VK_LCONTROL|Linke STRG-Taste|
|VK_LMENU|Linke Menütaste|
|VK_LSHIFT|Linke UMSCHALTTASTE|
|VK_MEDIA_NEXT_TRACK|Windows: Taste für nächsten Titel|
|VK_MEDIA_PLAY_PAUSE|Windows: Taste für abspielen/Pause-Medien|
|VK_MEDIA_PREV_TRACK|Windows: Taste für vorherigen Titel|
|VK_MEDIA_STOP|Windows: Beenden Sie die Taste für Medien|
|VK_MODECHANGE|IME-Modusänderungsanforderung|
|VK_NONCONVERT|IME-Nicht-Konvertierung|
|VK_OEM_1|Windows: Für die US-Standardtastatur die ";:' Schlüssel|
|VK_OEM_102|Windows: Entweder die Spitze Klammer oder den umgekehrten Schrägstrich-Taste auf der RT-102-Tasten-Tastatur|
|VK_OEM_2|Windows: Für die US-Standardtastatur die "/?" Key|
|VK_OEM_3|Windows: Für die US-Standardtastatur die "~" Schlüssel|
|VK_OEM_4|Windows: Für die US-Standardtastatur die "[{" Key|
|VK_OEM_5|Windows: Für die US-Standardtastatur die "\\&#124;' Schlüssel|
|VK_OEM_6|Windows: Für die US-Standardtastatur die "]}" Schlüssel|
|VK_OEM_7|Windows: Für die US-Standardtastatur die Taste "Single-Quote/doppelte Anführungszeichen"|
|VK_OEM_COMMA|Windows: Für alle Länder/Regionen, die ","-Taste|
|VK_OEM_MINUS|Windows: Für alle Länder/Regionen die '-' Schlüssel|
|VK_OEM_PERIOD|Windows: Für alle Länder/Regionen die '.' Schlüssel|
|VK_OEM_PLUS|Windows: Für alle Länder/Regionen, die Taste "+"|
|VK_PACKET|Windows: Wird verwendet, um Unicode-Zeichen zu übergeben, als wären sie Tastatureingaben.|
|VK_RCONTROL|Rechte STRG-Taste|
|VK_RMENU|Rechte Menütaste|
|VK_RSHIFT|Rechte UMSCHALTTASTE|
|VK_SLEEP|Taste für Standbymodus|
|VK_VOLUME_DOWN|Windows: Leiser-Taste|
|VK_VOLUME_MUTE|Windows: Taste zum Stummschalten|
|VK_VOLUME_UP|Windows: Lauter-Taste|
|VK_XBUTTON1|Windows: X1-Maustaste|
|VK_XBUTTON2|Windows: X2-Maustaste|

## <a name="associating-an-accelerator-key-with-a-menu-item"></a>Verknüpfen einer Zugriffstaste mit einem Menüelement

In vielen Fällen möchten Sie über ein Menüelement und eine Tastenkombination verfügen, um denselben Programmbefehl auszugeben. Hierzu weisen Sie dieselbe Ressourcen-ID zum Menüelement und zum Eintrag in der Zugriffstastentabelle Ihrer Anwendung zu. Sie können die Beschriftung des Menüelements ändern, um den Namen der Zugriffstaste anzuzeigen. Weitere Informationen über Menüelemente und Zugriffstasten finden Sie unter [Verknüpfen eines Menübefehls mit einer Zugriffstaste](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zugriffstasten-Editor](../windows/accelerator-editor.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)

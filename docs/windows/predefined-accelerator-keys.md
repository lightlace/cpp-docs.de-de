---
title: Zugriffstasten (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: bb407538f254df5f187ff91b85a8eaa753a52287
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362386"
---
# <a name="accelerator-keys-c"></a>Zugriffstasten (C++)

## <a name="predefined-accelerator-keys"></a>Vordefinierte Zugriffstasten

Es gibt eine Anzahl vordefinierter Zugriffstasten, die Teil eines Windows-Anwendungsprojekts sein können. Einige dieser virtuellen Tasten sind für die Windows-Umgebung. Andere unterstützen Browser oder Unicode-Anwendungen. Dieser Tasten können in beliebigen Zugriffstasten verwendet werden.

|Key|Beschreibung|
|---------|-----------------|
|VK_ACCEPT|(IME) akzeptieren|
|VK_BROWSER_BACK|(Windows) Browser **wieder** Schlüssel|
|VK_BROWSER_FAVORITES|(Windows) Browser **Favoriten** Schlüssel|
|VK_BROWSER_FORWARD|(Windows) Browser **Vorwärts** Schlüssel|
|VK_BROWSER_HOME|(Windows) Browser **starten** und **Startseite** Schlüssel|
|VK_BROWSER_REFRESH|(Windows) Browser **aktualisieren** Schlüssel|
|VK_BROWSER_SEARCH|(Windows) Browser **Suche** Schlüssel|
|VK_BROWSER_STOP|(Windows) Browser **beenden** Schlüssel|
|VK_CONVERT|(IME) konvertieren|
|VK_FINAL|Final-Modus (IME)|
|VK_HANGUEL|(IME) -Hanguel-Modus (aus Kompatibilitätsgründen beibehalten, verwenden Sie VK_HANGUL)|
|VK_HANGUL|(IME) Hangul-Modus|
|VK_HANJA|(IME) -Hanja-Modus|
|VK_JUNJA|(IME) -Junja-Modus|
|VK_KANA|(IME) Kana-Modus|
|VK_KANJI|(IME) Kanji-Modus|
|VK_LAUNCH_APP1|(Windows) **-Anwendung 1 starten** Schlüssel|
|VK_LAUNCH_APP2|(Windows) **Anwendung 2 starten** Schlüssel|
|VK_LAUNCH_MAIL|(Windows) **Mail starten** Schlüssel|
|VK_LAUNCH_MEDIA_SELECT|(Windows) **Medienauswahl** Schlüssel|
|VK_LCONTROL|**Linke STRG** Schlüssel|
|VK_LMENU|**Menü links** Schlüssel|
|VK_LSHIFT|**Left Shift** Schlüssel|
|VK_MEDIA_NEXT_TRACK|(Windows) **NextTrack** Schlüssel|
|VK_MEDIA_PLAY_PAUSE|(Windows) **Abspielen/Pause Media** Schlüssel|
|VK_MEDIA_PREV_TRACK|(Windows) **PreviousTrack** Schlüssel|
|VK_MEDIA_STOP|(Windows) **Beenden Media** Schlüssel|
|VK_MODECHANGE|(IME)-modusänderungsanforderung|
|VK_NONCONVERT|(IME) nonconvert|
|VK_OEM_1|(Windows) Für die US-Standardtastatur die **;:** Schlüssel|
|VK_OEM_102|(Windows) Entweder die Spitze Klammer oder den umgekehrten Schrägstrich-Taste auf der RT-102-Tasten-Tastatur|
|VK_OEM_2|(Windows) Für die US-Standardtastatur die **/?** Key|
|VK_OEM_3|(Windows) Für die US-Standardtastatur die **`~** Schlüssel|
|VK_OEM_4|(Windows) Für die US-Standardtastatur die **[{** Schlüssel|
|VK_OEM_5|(Windows) Für die US-Standardtastatur die **\\ &#124;** Schlüssel|
|VK_OEM_6|(Windows) Für die US-Standardtastatur die **]}** Schlüssel|
|VK_OEM_7|(Windows) Für die US-Standardtastatur die Taste "Single-Quote/doppelte Anführungszeichen"|
|VK_OEM_COMMA|(Windows) Für alle Länder/Regionen die **,** Schlüssel|
|VK_OEM_MINUS|(Windows) Für alle Länder/Regionen die **-** Schlüssel|
|VK_OEM_PERIOD|(Windows) Für alle Länder/Regionen die **.** Key|
|VK_OEM_PLUS|(Windows) Für alle Länder/Regionen die **+** Schlüssel|
|VK_PACKET|(Windows) Wird verwendet, um Unicode-Zeichen zu übergeben, als ob sie die Tastatureingaben sind.|
|VK_RCONTROL|**Rechte STRG** Schlüssel|
|VK_RMENU|**Menü "rechts"** Schlüssel|
|VK_RSHIFT|**Right Shift** Schlüssel|
|VK_SLEEP|**Standbymodus** Schlüssel|
|VK_VOLUME_DOWN|(Windows) **Leiser** Schlüssel|
|VK_VOLUME_MUTE|(Windows) **Stummschalten** Schlüssel|
|VK_VOLUME_UP|(Windows) **Lauter** Schlüssel|
|VK_XBUTTON1|(Windows) **X1** los|
|VK_XBUTTON2|(Windows) **X2** los|

## <a name="accelerator-key-association"></a>Accelerator-Key-Zuordnung

In vielen Fällen möchten Sie über ein Menüelement und eine Tastenkombination verfügen, um denselben Programmbefehl auszugeben. Sie führen Sie diese Aktion durch den gleichen Ressourcenbezeichner (ID) zuweisen, um das Menüelement und ein Eintrag in der Zugriffstastentabelle Ihrer Anwendung. Sie können die Beschriftung des Menüelements ändern, um den Namen der Zugriffstaste anzuzeigen. Weitere Informationen über Menüelemente und Zugriffstasten finden Sie unter [Menübefehle](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zugriffstasten-Editor](../windows/accelerator-editor.md)<br/>
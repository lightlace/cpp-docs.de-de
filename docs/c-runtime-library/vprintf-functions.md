---
title: vprintf-Funktionen
ms.date: 11/04/2016
apilocation:
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- vprintf
helpviewer_keywords:
- vprintf function
- formatted text [C++]
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
ms.openlocfilehash: c45197c9008c2d0b6a0519d947ca75f55a7960fd
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747845"
---
# <a name="vprintf-functions"></a>vprintf-Funktionen

Jede dieser `vprintf`-Funktionen verwendet einen Zeiger auf eine Argumentliste und formatiert und schreibt dann die angegebenen Daten in ein bestimmtes Ziel. Die Funktionen unterscheiden sich von der durchgeführten Parameterüberprüfung, unabhängig davon, ob die Funktionen Breit- oder Einzelbyte-Zeichenfolgen annehmen. Auch das Ausgabeziel und die Unterstützung für die Angabe der Reihenfolge, in der Parameter in der Formatzeichenfolge verwendet werden, spielen keine Rolle.

|||
|-|-|
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|
|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|
|[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|

## <a name="remarks"></a>Anmerkungen

Die `vprintf`-Funktionen verhalten sich ähnlich wie die entsprechenden Funktionen, die in der folgenden Tabelle aufgeführt werden. Allerdings akzeptiert jede `vprintf`-Funktion einen Zeiger auf eine Argumentliste, während jede der entsprechenden Funktionen eine Argumentliste akzeptiert.

Diese Funktionen formatieren Daten für die Ausgabe an die im Folgenden genannten Ziele.

|Funktion|Entsprechende Funktion|Ausgabeziel|Parametervalidierung|Unterstützung für positionale Parameter|
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|Konsole|Prüfen Sie auf NULL.|Nein|
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|Konsole|Prüfen Sie auf NULL.|Nein|
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Prüfen Sie auf NULL.|Nein|
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Stream*|Prüfen Sie auf NULL.|Nein|
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Stream*|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Stream*|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Prüfen Sie auf NULL.|Nein|
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Prüfen Sie auf NULL.|nein|
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL und ein gültiges Format.|ja|
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL und ein gültiges Format.|Nein|
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|Der auf *buffer* zeigende Speicher|Prüfen Sie auf NULL.|Nein|

Das Argument `argptr` weist den Typ `va_list` auf, der in VARARGS.H und STDARG.H definiert ist. Die Variable `argptr` muss durch **va_start** initialisiert werden und kann möglicherweise von nachfolgenden `va_arg`-Aufrufen initialisiert werden. Anschließend zeigt `argptr` auf den Anfang einer Liste von Argumenten, die für die Ausgabe gemäß den entsprechenden Angaben im *format*-Argument konvertiert und übertragen werden. *format* hat dieselbe Form und Funktion wie das Argument *format* für [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Durch keiner dieser Funktionen wird `va_end` aufgerufen. Eine umfassendere Beschreibung der einzelnen `vprintf`-Funktionen finden Sie in der Beschreibung der entsprechenden Funktion, wie in der obigen Tabelle aufgeführt wird.

`_vsnprintf` unterscheidet sich von **vsprintf** dahingehend, dass es nicht mehr als *count*-Bytes in *buffer* schreibt.

Die Versionen dieser Funktionen mit dem Infix **w** im Namen sind Breitzeichenversionen der entsprechenden Funktionen ohne das Infix **w**. In jeder dieser Breitzeichenfunktionen sind *buffer* und *format* Zeichenfolgen mit Breitzeichen. Anderenfalls verhält sich jede Breitzeichenfunktion identisch zu der entsprechenden SBCS-Funktion.

Die Versionen dieser Funktionen mit den Suffixen **_s** und **_p** sind Versionen mit höherer Sicherheit. Diese Versionen überprüfen die Formatzeichenfolgen und generieren eine Ausnahme, wenn die Formatzeichenfolge nicht wohlgeformt ist (z.B., wenn ungültige Formatierungszeichen verwendet werden).

Die Versionen dieser Funktionen mit dem Suffix **_p** bieten die Möglichkeit, die Reihenfolge anzugeben, in der die angegebenen Argumente in der Formatzeichenfolge ersetzt werden. Weitere Informationen finden Sie unter [printf-Positionsparameter](../c-runtime-library/printf-p-positional-parameters.md).

Wenn bei **vsprintf**, `vswprintf`, `_vsnprintf` und `_vsnwprintf` der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.

> [!IMPORTANT]
>  Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns). Wenn die sicheren Versionen dieser Funktionen (entweder die Suffixe **_s** oder **_p**) verwendet werden, könnte eine benutzerdefinierte Formatzeichenfolge eine Ausnahme aufgrund ungültiger Parameter auslösen, sofern die vom Benutzer bereitgestellte Zeichenfolge ungültige Formatierungszeichen enthält.

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)

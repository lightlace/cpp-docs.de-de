---
title: Zuordnungen für generischen Text in Tchar.h
ms.date: 11/04/2016
f1_keywords:
- tchar.h
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: 969894502689dd5aeeeaa27404bafc3c483c1336
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667583"
---
# <a name="generic-text-mappings-in-tcharh"></a>Zuordnungen für generischen Text in Tchar.h

Um das Transportieren von Code für die internationale Verwendung zu vereinfachen, stellt Microsoft-spezifische Zuordnungen für generischen Text von der Microsoft-Laufzeitbibliothek für viele Datentypen, Routinen und andere Objekte bereit. Diese Zuordnungen, die in Tchar.h, um die generischen Code schreiben, der für Einzelbyte-, Mehrbyte-kompiliert werden, können definiert werden können oder Unicode-Zeichensätze, abhängig von einer eindeutigen Konstante, die Sie definieren, mit einem `#define` Anweisung. Generische Textzuordnungen sind Microsoft-Erweiterungen, die nicht mit ANSI kompatibel sind.

Mit Tchar.h, können Sie Einzelbyte- und Mehrbyte-Zeichensätzen (MBCS) Unicode-Anwendungen aus denselben Quellen erstellen. Mit Tchar.h werden Makros (mit dem Präfix `_tcs`) definiert, die der Funktion `str`, `_mbs` oder `wcs` zugeordnet werden, vorausgesetzt, die Präprozessordefinitionen sind richtig. Definieren Sie zur Erstellung von MBCS das `_MBCS`-Symbol. Definieren Sie das Symbol zur Erstellung von Unicode `_UNICODE`. Um eine Einzelbyte-Anwendung zu erstellen, geben Sie nichts an (Standardeinstellung). Standardmäßig wird `_MBCS` für MFC-Anwendungen definiert.

Der `_TCHAR`-Datentyp wird in Tchar.h bedingt definiert. Wenn das Symbol `_UNICODE` wird definiert, für den Build, `_TCHAR` ist definiert als **"wchar_t"** ist, andernfalls für Einzelbyte- und MBCS-Builds als definiert **Char**. (**"wchar_t"**, die Unicode-Breitzeichen-Basisdatentyp, ist das 16-Bit-Gegenstück zu einem 8-Bit-signiert **Char**.) Verwenden Sie für internationale Anwendungen die `_tcs`-Funktionsreihe, bei der anstelle von Bytes `_TCHAR`-Einheiten verwendet werden. Z. B. `_tcsncpy` Kopien `n` `_TCHARs`, nicht `n` Bytes.

Da für einige Funktionen zur Zeichenfolgenbehandlung bei Einzelbyte-Zeichensätzen (SBCS) `char*`-Parameter (mit Vorzeichen) erforderlich sind, wird bei der Definition von `_MBCS` eine Compiler-Warnung ausgegeben, die auf einen Typenkonflikt hinweist. Es gibt drei Möglichkeiten, diese Warnung zu vermeiden:

1. Verwenden Sie die typsicheren Inlinefunktionsthunks in Tchar.h. Dies ist das Standardverhalten.

1. Verwenden Sie die direkten Makros in Tchar.h, indem Sie in der Befehlszeile `_MB_MAP_DIRECT` definieren. In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen. Dies ist die schnellste Methode; sie ist jedoch nicht typsicher.

1. Verwenden Sie die typsicheren statisch verknüpften Bibliotheksfunktionsthunks in Tchar.h. Definieren Sie hierzu in der Befehlszeile die Konstante `_NO_INLINING`. Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.

### <a name="preprocessor-directives-for-generic-text-mappings"></a>Präprozessordirektiven zum Zuordnen von generischem Text

|#define|Kompilierte Version|Beispiel|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode (Breitzeichen)|`_tcsrev` wird `_wcsrev` zugeordnet.|
|`_MBCS`|Mehrbytezeichen|`_tcsrev` wird `_mbsrev` zugeordnet.|
|Keine (bei der Standardeinstellung ist weder `_UNICODE` noch `_MBCS` definiert)|SBCS (ASCII)|`_tcsrev` wird `strrev` zugeordnet.|

Die in Tchar.h definierte generische Textfunktion `_tcsrev` wird z. B. der `_mbsrev`-Funktion zugeordnet, wenn Sie `_MBCS` in einem Programm definiert haben, oder sie wird `_wcsrev` zugeordnet, wenn Sie `_UNICODE` definiert haben. Andernfalls wird `_tcsrev` `strrev` zugeordnet. Zur Vereinfachung der Programmierung werden in Tchar.h weitere Datentypzuordnungen zur Verfügung gestellt; `_TCHAR` ist jedoch die hilfreichste Zuordnung.

### <a name="generic-text-data-type-mappings"></a>Generische Textzuordnungen von Datentypen

|Generischer Text<br /> Datentypname|_UNICODE &<br /> _MBCS nicht definiert|_MBCS<br /> Definiert|_UNICODE<br /> Definiert|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**char**|**char**|**wchar_t**|
|`_TINT`|**int**|**unsigned int**|`wint_t`|
|`_TSCHAR`|**Char mit Vorzeichen**|**Char mit Vorzeichen**|**wchar_t**|
|`_TUCHAR`|**unsigned char**|**unsigned char**|**wchar_t**|
|`_TXCHAR`|**char**|**unsigned char**|**wchar_t**|
|`_T` oder `_TEXT`|Ohne Auswirkung (wird vom Präprozessor entfernt)|Ohne Auswirkung (wird vom Präprozessor entfernt)|`L` (konvertiert das nächste Zeichen oder eine Zeichenfolge, die Unicode-Entsprechung)|

Eine Liste mit generischen textzuordnungen von Routinen, Variablen und andere Objekte, finden Sie unter [Zuordnungen für generischen Text](../c-runtime-library/generic-text-mappings.md) in der Run-Time Library Reference.

> [!NOTE]
>  Verwenden Sie die `str`-Funktionsreihe nicht mit Unicode-Zeichenfolgen, da diese wahrscheinlich eingebettete NULL-Bytes enthalten. Ebenso sollten Sie die `wcs`-Funktionsreihe nicht mit Zeichenfolgen vom Typ MBCS (oder SBCS) verwenden.

Aus den folgenden Codefragmenten geht hervor, wie `_TCHAR` und `_tcsrev` für die Zuordnung zu den MBCS-, Unicode- und SBCS-Modellen verwendet werden.

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

Wenn `_MBCS` definiert wurde, ordnet der Präprozessor diesem Code folgenden Ausschnitt zu:

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

Wenn `_UNICODE` definiert wurde, ordnet der Präprozessor diesem Code folgenden Ausschnitt zu:

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

Wenn weder `_MBCS` noch `_UNICODE` wurden definiert, ordnet der Präprozessor das Fragment Einzelbyte-ASCII-Code wie folgt:

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

Folglich können Sie eine einzige Quellcodedatei so schreiben, verwalten und kompilieren, dass sie mit Routinen ausgeführt wird, die jeweils speziell auf einen der drei Zeichensätze ausgerichtet sind.

## <a name="see-also"></a>Siehe auch

[Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)<br/>
[Verwenden von TCHAR.H-Datentypen in _MBCS-Code](../text/using-tchar-h-data-types-with-mbcs-code.md)
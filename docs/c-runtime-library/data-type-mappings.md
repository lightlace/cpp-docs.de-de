---
title: Datentypzuordnungen
ms.date: 11/04/2016
f1_keywords:
- _TXCHAR
- _TUCHAR
- _TINT
- _TSCHAR
- _TCHAR
- TCHAR::H
- TCHAR
- _T
- _TEXT
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- TXCHAR type
- _TSCHAR type
- T type
- _TUCHAR type
- _TEXT type
- _T type
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
ms.openlocfilehash: 3d6e43d8d39cb208efbb6010ef2591a2880fd584
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647897"
---
# <a name="data-type-mappings"></a>Datentypzuordnungen

Diese Datentypzuordnungen werden in TCHAR.H definiert und hängen davon ab, ob die Konstante `_UNICODE` oder die Konstante `_MBCS` im Programm definiert wurde.

Entsprechende Informationen finden Sie unter [Using TCHAR.H Data Types with _MBCS Code (Verwenden von TCHAR.H-Datentypen in _MBCS-Code)](../text/using-tchar-h-data-types-with-mbcs-code.md).

### <a name="generic-text-data-type-mappings"></a>Generische Textzuordnungen von Datentypen

|Generischer Textname von<br /><br /> Datentypen|SBCS (_UNICODE,<br /><br /> _MBCS nicht<br /><br /> definiert)|_MBCS<br /><br /> Definition|_UNICODE<br /><br /> Definition|
|--------------------------------------|----------------------------------------------------|------------------------|---------------------------|
|`_TCHAR`|`char`|`char`|`wchar_t`|
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|
|`_TINT`|`int`|`int`|`wint_t`|
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|
|`_T` oder `_TEXT`|Ohne Auswirkung (wird vom Präprozessor entfernt)|Ohne Auswirkung (wird vom Präprozessor entfernt)|`L` (konvertiert das nächste Zeichen oder die nächste Zeichenfolge in die Unicode-Entsprechung)|

## <a name="see-also"></a>Siehe auch

[Allgemeintext-Zuordnungen](../c-runtime-library/generic-text-mappings.md)<br/>
[Zuordnungen von Konstanten und globalen Variablen](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[Routinezuordnungen](../c-runtime-library/routine-mappings.md)<br/>
[Beispiel für ein Programm mit generischem Text](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Using Generic-Text Mappings (Verwenden von Zuordnungen für generischen Text)](../c-runtime-library/using-generic-text-mappings.md)
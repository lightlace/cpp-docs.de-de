---
title: Land/Region-Zeichenfolgen
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: 49eb6bc4473d9e54c06c3bf9290f8c3c96640415
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500249"
---
# <a name="countryregion-strings"></a>Sprache/Land-Zeichenfolgen

Zeichenfolgen für Länder und Regionen können mit einer Sprachenzeichenfolge kombiniert werden, um eine Gebietsschemaspezifikation für die Funktionen `setlocale`, `_wsetlocale`, `_create_locale`und `_wcreate_locale` zu erstellen. Eine Liste der von den verschiedenen Windows-Betriebssystemversionen unterstützten Länder und Regionen finden Sie in den Spalten **Language** (Sprache), **Location** (Ort) und **Language Tag** (Sprachtag) der Tabelle in [Appendix A: Product Behavior](https://msdn.microsoft.com/library/cc233982.aspx) (Anhang A: Produktverhalten) in [MS-LCID]: Windows Language Code Identifier (LCID) Reference (LCID-Referenz [Windows Language Code Identifier]). Ein Beispiel für Code, der verfügbare Gebietsschemanamen und zugehörige Werte aufzählt, finden Sie unter [NLS: Name-based APIs Sample](/windows/win32/intl/nls--name-based-apis-sample) (Beispiel für namensbasierte APIs).

## <a name="additional-supported-country-and-region-strings"></a>Weitere unterstützte Zeichenfolgen für Länder und Regionen

Die Implementierung der Microsoft C-Laufzeitbibliothek unterstützt auch die folgenden zusätzlichen Land-/Regionszeichenfolgen und Abkürzungen:

|Land-/Regionszeichenfolge|Abkürzung|Entsprechender Gebietsschemaname|
|----------------------------|------------------|----------------------------|
|america|USA|en-US|
|britain|GBR|en-GB|
|china|CHN|zh-CN|
|czech|CZE|cs-CZ|
|england|GBR|en-GB|
|great britain|GBR|en-GB|
|holland|NLD|nl-NL|
|hong-kong|HKG|zh-HK|
|new-zealand|NZL|en-NZ|
|nz|NZL|en-NZ|
|pr china|CHN|zh-CN|
|pr-china|CHN|zh-CN|
|puerto-rico|PRI|es-PR|
|slovak|SVK|sk-SK|
|south africa|ZAF|af-ZA|
|south korea|KOR|ko-KR|
|south-africa|ZAF|af-ZA|
|south-korea|KOR|ko-KR|
|trinidad & tobago|TTO|en-TT|
|uk|GBR|en-GB|
|united-kingdom|GBR|en-GB|
|united-states|USA|en-US|
|mehreren|USA|en-US|

## <a name="see-also"></a>Siehe auch

[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Language Strings](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)

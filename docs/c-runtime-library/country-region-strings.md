---
title: Zeichenfolgen für Länder und Regionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f227feec25e3b487772f8e469651f08be825419f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605629"
---
# <a name="countryregion-strings"></a>Country/Region Strings

Zeichenfolgen für Länder und Regionen können mit einer Sprachenzeichenfolge kombiniert werden, um eine Gebietsschemaspezifikation für die Funktionen `setlocale`, `_wsetlocale`, `_create_locale`und `_wcreate_locale` zu erstellen. Eine Liste der von den verschiedenen Windows-Betriebssystemversionen unterstützten Länder und Regionen finden Sie unter **Sprache**, **Ort** in der Spalte **Sprachtag** der Tabelle unter [Anhang A: Produktverhalten](https://msdn.microsoft.com/library/cc233982.aspx) in [MS-LCID]: Windows-Sprachcodebezeichner – Referenz. Ein Beispiel für Code, der verfügbare Gebietsschemanamen und zugehörige Werte aufzählt, finden Sie unter [NLS: Namenbasierte APIs – Beispiel](/windows/desktop/intl/nls--name-based-apis-sample).

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

[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
[Language Strings](../c-runtime-library/language-strings.md)  
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)  
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)  

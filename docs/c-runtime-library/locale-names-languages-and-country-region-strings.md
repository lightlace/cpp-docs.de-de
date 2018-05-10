---
title: Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder und Regionen | Microsoft-Dokumentation
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
- localization, locale
- locales
- setlocale function
- language strings
ms.assetid: a0e5a0c5-5602-4da0-b65f-de3d6c8530a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeaeb21dfabac173b639fe4b3e1518b276c629a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="locale-names-languages-and-countryregion-strings"></a>Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen
Das *locale*-Argument für die Funktionen `setlocale` und `_create_locale` kann mithilfe der Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages festgelegt werden, die von der Windows NLS API unterstützt werden. Das *locale*-Argument weist folgende Form auf:  
  
> *locale* :: "*locale_name*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "*language*\[\_*country-region*]\[.*code_page*]]"  
&nbsp;&nbsp;&nbsp;&nbsp;| ".*code_page*"  
&nbsp;&nbsp;&nbsp;&nbsp;| "C"  
&nbsp;&nbsp;&nbsp;&nbsp;| ""  
&nbsp;&nbsp;&nbsp;&nbsp;| NULL  
  
 Die Form des Gebietsschemanamens wird bevorzugt. Verwenden Sie z.B. `en-US` für Englisch (USA) oder `bs-Cyrl-BA` für Bosnisch (Kyrillisch, Bosnien und Herzegowina). Der Satz von Gebietsschemanamen wird in [Gebietsschemanamen](http://msdn.microsoft.com/library/windows/desktop/dd373814.aspx)beschrieben. Eine Auflistung aller von der Version des Windows-Betriebssystems unterstützten Gebietsschemanamen enthält die Spalte des **Kulturnamens** unter der [Referenz zur NLS(National Language Support)-API](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Unter dieser Ressource finden Sie die unterstützte Sprache, das Skript und die regionalen Teile der Gebietsschemanamen. Informationen zu den unterstützten Gebietsschemanamen ohne standardmäßige Sortierreihenfolge finden Sie in der Spalte des **Gebietsschemanamens** unter den [Sortierreihenfolgen-IDs](http://msdn.microsoft.com/library/windows/desktop/dd374060.aspx). Weitere Informationen zur Sprach-und Ortsunterstützung in Windows-Betriebssystemen nach Version finden Sie unter [Appendix A: Product Behavior](http://msdn.microsoft.com/goglobal/bb896001.aspx) in „[MS-LCID]: Windows Language Code Identifier (LCID) Reference“ (Anhang A: Produktverhalten in „[MS-LCID]: Windows-Sprachcodebezeichner – Referenz“). Unter Windows 10 und höher sind Gebietsschemanamen zulässig, die gültigen BCP-47-Sprachtags entsprechen. `jp-US` z.B. ist ein gültiges BCP-47-Tag, für die locale-Funktion ist es jedoch effektiv nur `US`.  
  
 Die Form *language*[*_country_region*[.*code_page*]] wird in den lokalen Einstellungen für eine Kategorie gespeichert, wenn eine Sprachenzeichenfolge oder Sprachenzeichenfolge und Land-/Regionszeichenfolge verwendet wird, um das Gebietsschema zu erstellen. Der Satz von unterstützten Sprachenzeichenfolgen wird in [Language Strings](../c-runtime-library/language-strings.md)beschrieben, und die Liste der unterstützten Länder-/Regionszeichenfolgen wird in [Country/Region Strings](../c-runtime-library/country-region-strings.md)aufgeführt. Wenn die angegebene Sprache nicht zu dem angegebenen Land bzw. der angegebenen Region zugeordnet ist, wird in den lokalen Einstellungen die Standardsprache für das angegebene Land bzw. die angegebene Region gespeichert. Für Gebietsschema-Zeichenfolgen, die in Code eingebettet sind oder für den Speicher serialisiert sind, empfehlen wir diese Form nicht. Bei diesen Zeichenfolgen ist nämlich die Wahrscheinlichkeit größer, dass sie durch eine Betriebssystemaktualisierung geändert werden, als die Gebietsschema-Namensform.  
  
 Die dem Gebietsschema zugeordnete Codepage ist die ANSI/OEM-Codepage. Die Codepage wird für Sie festgelegt, wenn Sie ein Gebietsschema nur nach Sprache oder nach Sprache und Land/Region angeben. Der spezielle Wert `.ACP` gibt die ANSI-Codepage für das Land bzw. die Region an. Der spezielle Wert `.OCP` gibt die OEM-Codepage für das Land bzw. die Region an. Wenn Sie beispielsweise `"Greek_Greece.ACP"` als das Gebietsschema angeben, wird das Gebietsschema als `Greek_Greece.1253` (die ANSI-Codepage für Griechisch) gespeichert, und wenn Sie `"Greek_Greece.OCP"` als das Gebietsschema angegeben, wird es als `Greek_Greece.737` (die OEM-Codepage für Griechisch) gespeichert. Weitere Informationen zu Codepages finden Sie unter [Code Pages](../c-runtime-library/code-pages.md). Eine Liste der unter Windows unterstützten Codepages finden Sie unter den [Codepage-IDs](http://msdn.microsoft.com/library/windows/desktop/dd317756.aspx).  
  
 Wenn Sie nur die Codepage zum Angeben des Gebietsschemas verwenden, werden Standardsprache und Standardland/-region des Systems verwendet. Wenn Sie beispielsweise `".1254"` (ANSI-Code für Türkisch) als Gebietsschema in einem für Englisch (USA) konfigurierten System angeben, wird `English_United States.1254`als Gebietsschema gespeichert. Die Verwendung dieser Form wird nicht empfohlen, da sie zu inkonsistentem Verhalten führen kann.  
  
Ein *locale*-Argumentwert von `C` gibt die Umgebung mit minimaler ANSI-Konformität für die C-Übersetzung an. Das `C` -Gebietsschema geht davon aus, dass jeder `char` -Datentyp 1 Byte und sein Wert immer kleiner als 256 ist. Wenn *locale* auf eine leere Zeichenfolge zeigt, ist das Gebietsschema die durch die Implementierung definierte native Umgebung.  
  
Sie können für die Funktionen `setlocale` und `_wsetlocale` alle Gebietsschemakategorien gleichzeitig mithilfe der `LC_ALL` -Kategorie angeben. Die Kategorien können alle auf das gleiche Gebietsschema festgelegt werden, oder Sie können jede Kategorie einzeln festlegen, indem Sie ein Gebietsschemaargument mit dieser Form verwenden:  
  
> LC_ALL_specifier :: locale  
&nbsp;&nbsp;&nbsp;&nbsp;| [LC_COLLATE=locale][;LC_CTYPE=locale][;LC_MONETARY=locale][;LC_NUMERIC=locale][;LC_TIME=locale]  
  
Sie können mehrere Kategorientypen angeben, durch Semikolons getrennt. Bei nicht angegebenen Kategorientypen werden die aktuellen Gebietsschemaeinstellungen verwendet. Dieser Codeausschnitt legt beispielsweise das aktuelle Gebietsschema für alle Kategorien auf `de-DE` fest und legt dann die Kategorien `LC_MONETARY` auf `en-GB` und `LC_TIME` auf `es-ES` fest:  
  
```C  
_wsetlocale(LC_ALL, L"de-DE");  
_wsetlocale(LC_ALL, L"LC_MONETARY=en-GB;LC_TIME=es-ES");  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C-Laufzeitbibliotheksreferenz](../c-runtime-library/c-run-time-library-reference.md)   
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Sprachzeichenfolgen](../c-runtime-library/language-strings.md)   
 [Länder-/Regionszeichenfolgen](../c-runtime-library/country-region-strings.md)
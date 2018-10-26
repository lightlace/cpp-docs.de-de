---
title: Zeichenfolgenkonvertierungs-Makros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa44449c65dbdfdea93004fa2fe1adffdeba033d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061740"
---
# <a name="string-conversion-macros"></a>Zeichenfolgenkonvertierungs-Makros

Diese Makros stellen Zeichenfolge Konvertierung-Funktionen.

##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL und MFC-Zeichenfolgen-Konvertierungsmakros

Die hier besprochenen Zeichenfolgenkonvertierungsmakros sind sowohl für ATL als auch für MFC gültig. Weitere Informationen zu MFC-zeichenfolgenkonvertierung, finden Sie unter [TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) und [MFC-Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE und TEXTMETRIC Zeichenfolgen-Konvertierungsmakros

Diese Makros Erstellen einer Kopie einer [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) oder [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) -Struktur und die Zeichenfolgen in die neue Struktur in einen neuen Zeichenfolgen-Datentyp zu konvertieren. Die Makros Zuordnen von Speicher auf dem Stapel für die neue Struktur und einen Zeiger auf die neue Struktur zurück.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Hinweise

Zum Beispiel:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

und:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

In den Makronamen der String-Datentyp in der Struktur, die auf der linken Seite ist (z. B. **ein**) und der String-Datentyp in der Zielstruktur auf der rechten Seite ist (z. B. **W**). **Ein** steht für LPSTR, **OLE** steht für LPOLESTR, **T** steht für LPTSTR, und **W** steht für LPWSTR.

Daher DEVMODEA2W kopiert eine `DEVMODE` Struktur mit LPSTR Zeichenfolgen in eine `DEVMODE` Struktur mit LPWSTR Zeichenfolgen TEXTMETRICOLE2T Kopien einer `TEXTMETRIC` Struktur mit LPOLESTR Zeichenfolgen in eine `TEXTMETRIC` Struktur, deren LPTSTR Zeichenfolgen usw.

Die beiden Zeichenfolgen konvertiert die `DEVMODE` Struktur sind, den Gerätenamen (`dmDeviceName`) und den Namen des Formulars (`dmFormName`). Die `DEVMODE` Zeichenfolgen-konvertierungsmakros auch aktualisieren, die Größe der Struktur (`dmSize`).

Die vier Zeichenfolgen konvertiert die `TEXTMETRIC` Struktur werden das erste Zeichen (`tmFirstChar`), das letzte Zeichen (`tmLastChar`), das Standardzeichen (`tmDefaultChar`), und die Umbruchzeichen (`tmBreakChar`).

Das Verhalten der `DEVMODE` und `TEXTMETRIC` Zeichenfolgen-konvertierungsmakros hängt von der Compilerdirektive gültig, die ggf. Wenn die Quell- und Zieltypen gleich sind, findet keine Konvertierung statt. Ändern Sie die Compiler-Direktiven **T** und **OLE** wie folgt:

|Geltende Compiler-Anweisung|T wird zu|OLE wird zu|
|----------------------------------|---------------|-----------------|
|Keine|**A**|**W**|
|**\_UNICODE**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|**\_UNICODE** und **OLE2ANSI**|**W**|**A**|

Die folgende Tabelle enthält die `DEVMODE` und `TEXTMETRIC` zeichenfolgenkonvertierungs-Makros.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)

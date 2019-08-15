---
title: Zeichen folgen Konvertierungs Makros
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: f7d9548fc5710e8d3d5d668dff230a60e7a291a1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495192"
---
# <a name="string-conversion-macros"></a>Zeichen folgen Konvertierungs Makros

Diese Makros Stellen Zeichen folgen Konvertierungs Funktionen bereit.

##  <a name="atl_and_mfc_string_conversion_macros"></a>ATL-und MFC-Zeichen folgen Konvertierungs Makros

Die hier besprochenen Zeichenfolgenkonvertierungsmakros sind sowohl für ATL als auch für MFC gültig. Weitere Informationen zur MFC-Zeichenfolgenkonvertierung finden Sie unter [TN059: Verwenden von MFC MBCS/Unicode-](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) Konvertierungs Makros und [MFC-Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md).

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>Zeichen folgen Konvertierungs Makros für DEVMODE und TextMetric

Diese Makros erstellen eine Kopie einer [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) -oder [TextMetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) -Struktur und konvertieren die Zeichen folgen innerhalb der neuen-Struktur in einen neuen Zeichen Folgentyp. Die Makros weisen dem Stapel Speicher für die neue-Struktur zu und geben einen Zeiger auf die neue-Struktur zurück.

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Hinweise

Beispiel:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

und:

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

In den Makronamen befindet sich der Zeichen folgenyp in der Quell Struktur auf der linken Seite (z. b. **A**), und der Zeichen Folgentyp in der Zielstruktur befindet sich auf der rechten Seite (z. b. **W**). **A** steht für LPStr, **OLE** steht für lpolestr, **T** für LPTSTR und **W** für LPWSTR.

Daher `DEVMODE` kopiert DEVMODEA2W eine Struktur mit LPStr-Zeichen folgen in eine `DEVMODE` Struktur mit LPWSTR-Zeichen folgen, `TEXTMETRIC` TEXTMETRICOLE2T kopiert eine Struktur mit lpolestr `TEXTMETRIC` -Zeichen folgen in eine Struktur mit LPTSTR-Zeichen folgen usw.

Die beiden Zeichen folgen, die `DEVMODE` in der-Struktur konvertiert werden`dmDeviceName`, sind der Gerätename (`dmFormName`) und der Formular Name (). Die `DEVMODE` Makros für die Zeichen folgen Konvertierung aktualisieren ebenfalls die`dmSize`Struktur Größe ().

Die vier Zeichen folgen, die `TEXTMETRIC` in der-Struktur konvertiert werden`tmFirstChar`, sind das erste Zeichen (`tmLastChar`), das letzte Zeichen (`tmDefaultChar`), das Standard Zeichen ()`tmBreakChar`und das Break-Zeichen ().

Das Verhalten `DEVMODE` der-und `TEXTMETRIC` -Zeichen folgen Konvertierungs Makros hängt von der entsprechenden Compilerdirektive ab, sofern vorhanden. Wenn die Quell- und Zieltypen gleich sind, findet keine Konvertierung statt. Die Compilerdirektiven ändern **T** und **OLE** wie folgt:

|Geltende Compiler-Anweisung|T wird zu|OLE wird zu|
|----------------------------------|---------------|-----------------|
|none|**A**|**W**|
|**\_UNICODE-**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|Unicode und **OLE2ANSI**  **\_**|**W**|**A**|

In der folgenden Tabelle sind `DEVMODE` die `TEXTMETRIC` -und Zeichen folgen Konvertierungs Makros aufgeführt.

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>Siehe auch

[Makros](../../atl/reference/atl-macros.md)

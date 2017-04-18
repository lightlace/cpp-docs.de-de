---
title: String-Makros zur Zeichenfolgenkonvertierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: e322c3af297c288ec6c9ccdb1c04e58d0a5759ff
ms.lasthandoff: 04/12/2017

---
# <a name="string-conversion-macros"></a>Zeichenfolgen-Konvertierungsmakros
Diese Makros stellen Zeichenfolge Konvertierung-Funktionen.  
  
 
##  <a name="atl_and_mfc_string_conversion_macros"></a>ATL und MFC-Makros zur Zeichenfolgenkonvertierung  
 Die hier besprochenen Zeichenfolgenkonvertierungsmakros sind sowohl für ATL als auch für MFC gültig. Weitere Informationen zu MFC-zeichenfolgenkonvertierung, finden Sie unter [TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) und [MFC-Makros und Globals](../../mfc/reference/mfc-macros-and-globals.md).  
  
##  <a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE und TEXTMETRIC Zeichenfolgen-Konvertierungsmakros  
 Diese Makros erstellen Sie eine Kopie einer [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) oder [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) Struktur und die Zeichenfolgen in der neuen Struktur in einen neuen Zeichenfolgen-Datentyp zu konvertieren. Die Makros Zuordnen von Speicher auf dem Stapel für die neue Struktur und einen Zeiger auf die neue Struktur zurück.  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Utilities #128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 und:  
  
 [!code-cpp[NVC_ATL_Utilities #129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 In den Makronamen der String-Datentyp in der Quellstruktur befindet sich auf der linken Seite (z. B. **ein**) und der String-Datentyp in der Zielstruktur auf der rechten Seite ist (z. B. **W**). **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 Daher `DEVMODEA2W` Kopien einer `DEVMODE` Struktur mit **LPSTR** Zeichenfolgen in ein `DEVMODE` Struktur mit `LPWSTR` Zeichenfolgen, `TEXTMETRICOLE2T` Kopien eine `TEXTMETRIC` Struktur mit `LPOLESTR` Zeichenfolgen, die in eine `TEXTMETRIC` Struktur mit `LPTSTR` Zeichenfolgen usw.  
  
 Die beiden Zeichenfolgen konvertiert, die der `DEVMODE` Struktur werden der Name des Laufwerks ( **DmDeviceName**) und den Namen des Formulars ( **DmFormName**). Die `DEVMODE` zeichenfolgenkonvertierungsmakros auch aktualisieren, die Größe der Struktur ( **DmSize**).  
  
 Die vier Zeichenfolgen konvertiert, die der `TEXTMETRIC` Struktur werden das erste Zeichen ( **TmFirstChar**), das letzte Zeichen ( **TmLastChar**), des Standardzeichensatzes ( **TmDefaultChar**), und die Umbruchzeichen ( **TmBreakChar**).  
  
 Das Verhalten der `DEVMODE` und `TEXTMETRIC` Makros zur zeichenfolgenkonvertierung hängt die Compiler-diretive, sofern vorhanden. Wenn die Quell- und Zieltypen gleich sind, findet keine Konvertierung statt. Ändern Sie die Compilerdirektiven **T** und **OLE** wie folgt:  
  
|Geltende Compiler-Anweisung|T wird zu|OLE wird zu|  
|----------------------------------|---------------|-----------------|  
|Keine|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE** und **OLE2ANSI**|**W**|**A**|  
  
 Die folgende Tabelle enthält die `DEVMODE` und `TEXTMETRIC` konvertierungsmakros Zeichenfolge.  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)



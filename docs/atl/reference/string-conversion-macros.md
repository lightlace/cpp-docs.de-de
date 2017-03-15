---
title: Konvertierungsmakros Zeichenfolge | Microsoft-Dokumentation
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
ms.sourcegitcommit: 89790d1a56f64e6479ae32d72c529142ba8df1de
ms.openlocfilehash: 0dce243b0f7db087db908d603e6cd1cfc4b02db8
ms.lasthandoff: 02/24/2017

---
# <a name="string-conversion-macros"></a>Zeichenfolgenkonvertierungsmakros
Diese Makros stellen Zeichenfolge Konvertierung-Funktionen.  
  
|||  
|-|-|  
|[ATL- und MFC-Makros zur Zeichenfolgenkonvertierung](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863)|Satz von Makros, die zwischen Zeichenfolgentypen konvertiert werden.|  
|[DEVMODE und TEXTMETRIC Zeichenfolgenkonvertierungsmakros](http://msdn.microsoft.com/library/85cebec0-2a18-48e5-9c1c-99d5b7f15425)|Satz von Makros, die in Zeichenfolgen konvertieren `DEVMODE` und `TEXTMETRIC` Strukturen.|  
  
##  <a name="a-nameatlandmfcstringconversionmacrosa--atl-and-mfc-string-conversion-macros"></a><a name="atl_and_mfc_string_conversion_macros"></a>ATL- und MFC-Makros zur Zeichenfolgenkonvertierung  
 Die hier besprochenen Zeichenfolgenkonvertierungsmakros sind sowohl für ATL als auch für MFC gültig. Weitere Informationen auf der MFC-zeichenfolgenkonvertierung finden Sie unter [TN059: Verwenden von MFC MBCS/Unicode-Konvertierungsmakros](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md) und [MFC-Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md).  
  
##  <a name="a-namedevmodeandtextmetricstringconversionmacrosa--devmode-and-textmetric-string-conversion-macros"></a><a name="devmode_and_textmetric_string_conversion_macros"></a>DEVMODE und TEXTMETRIC Zeichenfolgenkonvertierungsmakros  
 Diese Makros Erstellen einer Kopie einer [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) oder [TEXTMETRIC](http://msdn.microsoft.com/library/windows/desktop/dd145132) Struktur und die Zeichenfolgen in die neue Struktur in eine neue String-Datentyp konvertieren. Die Makros Speicher auf dem Stapel für die neue Struktur und einen Zeiger auf die neue Struktur zurück.  
  
```
MACRONAME( address_of_structure )
```  
  
### <a name="remarks"></a>Hinweise  
 Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_Utilities&#128;](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]  
  
 und:  
  
 [!code-cpp[NVC_ATL_Utilities&#129;](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]  
  
 In den Makronamen der String-Datentyp in der Quellstruktur, die auf der linken Seite ist (z. B. **ein**) und der String-Datentyp in der Zielstruktur auf der rechten Seite ist (z. B. **W**). **A** stands for **LPSTR**, **OLE** stands for `LPOLESTR`, **T** stands for `LPTSTR`, and **W** stands for `LPWSTR`.  
  
 Folglich `DEVMODEA2W` Kopien einer `DEVMODE` Struktur mit **LPSTR** Textzeichenfolgen in eine `DEVMODE` Struktur mit `LPWSTR` Zeichenfolgen `TEXTMETRICOLE2T` Kopien eine `TEXTMETRIC` Struktur mit `LPOLESTR` Textzeichenfolgen in eine `TEXTMETRIC` Struktur mit `LPTSTR` Zeichenfolgen usw..  
  
 Die beiden Zeichenfolgen konvertiert, die der `DEVMODE` Struktur werden der Gerätename ( **DmDeviceName**) und den Namen des Formulars ( **DmFormName**). Die `DEVMODE` zeichenfolgenkonvertierungsmakros aktualisiert auch die Größe der Struktur ( **DmSize**).  
  
 Die vier Zeichenfolgen konvertiert, die der `TEXTMETRIC` Struktur werden das erste Zeichen ( **TmFirstChar**), das letzte Zeichen ( **TmLastChar**), das Standardzeichen ( **TmDefaultChar**), und die Umbruchzeichen ( **TmBreakChar**).  
  
 Das Verhalten der `DEVMODE` und `TEXTMETRIC` zeichenfolgenkonvertierungsmakros hängt die Compilerdirektive wirksam, sofern vorhanden. Wenn die Quell- und Zieltypen gleich sind, findet keine Konvertierung statt. Ändern Sie die Compiler-Direktiven **T** und **OLE** wie folgt:  
  
|Geltende Compiler-Anweisung|T wird zu|OLE wird zu|  
|----------------------------------|---------------|-----------------|  
|Keine|**A**|**W**|  
|**_UNICODE**|**W**|**W**|  
|**OLE2ANSI**|**A**|**A**|  
|**_UNICODE** und **OLE2ANSI**|**W**|**A**|  
  
 Die folgende Tabelle enthält die `DEVMODE` und `TEXTMETRIC` konvertierungsmakros Zeichenfolge.  
  
### <a name="devmode-and-textmetric-string-conversion-macros"></a>DEVMODE und TEXTMETRIC Zeichenfolgenkonvertierungsmakros  
  
|||  
|-|-|  
|`DEVMODEA2W`|`TEXTMETRICA2W`|  
|`DEVMODEOLE2T`|`TEXTMETRICOLE2T`|  
|`DEVMODET2OLE`|`TEXTMETRICT2OLE`|  
|`DEVMODEW2A`|`TEXTMETRICW2A`|  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)



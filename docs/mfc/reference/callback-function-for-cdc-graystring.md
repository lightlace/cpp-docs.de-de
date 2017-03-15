---
title: "Rückruffunktion für CDC:: graystring | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::GrayString
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::GrayString
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3ce3afefae9618420a8a97b27994c33604745677
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcgraystring"></a>Rückruffunktion für CDC::GrayString
*OutputFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellten Rückruffunktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
#### <a name="parameters"></a>Parameter  
 `hDC`  
 Identifiziert einen Gerätekontext Speicher mit einer Bitmap mit mindestens der Breite und Höhe, die durch angegebene `nWidth` und `nHeight` auf `GrayString`.  
  
 `lpData`  
 Zeigt auf die zu zeichnende Zeichenfolge.  
  
 `nCount`  
 Gibt die Anzahl der Zeichen ausgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Callback-Funktion zurückgegebene Wert muss **TRUE** für eine erfolgreiche Ausführung; andernfalls ist es **FALSE**.  
  
## <a name="remarks"></a>Hinweise  
 Die Callback-Funktion (*OutputFunc*) müssen Zeichnen eines Bilds relativ zu den Koordinaten (0,0) statt (*x*, *y*).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring)



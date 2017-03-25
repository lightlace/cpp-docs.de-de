---
title: "Von MFC verwendete Rückruffunktionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
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
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 08c6f547c95adb4c6794ec71259888d390e42e92
ms.lasthandoff: 03/06/2017

---
# <a name="callback-functions-used-by-mfc"></a>Von MFC verwendete Rückruffunktionen
Drei Callback-Funktionen werden in der Microsoft Foundation Class-Bibliothek angezeigt. Diese Callback-Funktionen übergeben werden, um [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring), und [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc). Beachten Sie, dass alle Rückruffunktionen vor der Rückgabe auf Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht MFC-Ausnahmen abfangen müssen. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  

|Name||  
|----------|-----------------|  
|[Rückruffunktion für CDC::EnumObjects](#enum_objects)||  
|[Rückruffunktion für CDC::GrayString](#graystring)||
|[Rückruffunktion für CDC::SetAbortProc](#setabortproc)|| 

## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h 

## <a name="enum_objects"></a>Rückruffunktion für CDC:: EnumObjects
Die *ObjectFunc* Name ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.  
  
### <a name="syntax"></a>Syntax  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszLogObject*  
 Verweist auf eine [LOGPEN](../../mfc/reference/logpen-structure.md) oder [LOGBRUSH](../../mfc/reference/logbrush-structure.md) -Datenstruktur, die Informationen über die logische Attribute des Objekts enthält.  
  
 `lpData`  
 Verweist auf die von der Anwendung bereitgestellten Daten übergeben, um die `EnumObjects` Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Callback-Funktion gibt eine `int`. Der Wert von diesem Return ist benutzerdefiniert. Wenn die Callback-Funktion gibt 0 zurück `EnumObjects` Enumeration vorzeitig beendet.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss exportiert werden.  
  
## <a name="graystring"></a>Rückruffunktion für CDC:: graystring
*OutputFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellten Rückruffunktion.  
  
### <a name="syntax"></a>Syntax  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Identifiziert einen Gerätekontext Speicher mit einer Bitmap mit mindestens der Breite und Höhe, die durch angegebene `nWidth` und `nHeight` auf `GrayString`.  
  
 `lpData`  
 Zeigt auf die zu zeichnende Zeichenfolge.  
  
 `nCount`  
 Gibt die Anzahl der Zeichen ausgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Callback-Funktion zurückgegebene Wert muss **TRUE** für eine erfolgreiche Ausführung; andernfalls ist es **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die Callback-Funktion (*OutputFunc*) müssen Zeichnen eines Bilds relativ zu den Koordinaten (0,0) statt (*x*, *y*).  

## <a name="setabortproc"></a>Rückruffunktion für CDC:: setabortproc
Der Name *AbortFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.  
  
### <a name="syntax"></a>Syntax  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
### <a name="parameters"></a>Parameter  
 *hPr*  
 Identifiziert den Gerätekontext.  
  
 `code`  
 Gibt an, ob ein Fehler aufgetreten ist. Es ist 0, wenn kein Fehler aufgetreten ist. Es ist **SP_OUTOFDISK** den Druck-Manager ist derzeit kein Speicherplatz mehr und mehr Speicherplatz verfügbar wird, wenn die Anwendung wartet. Wenn `code` ist **SP_OUTOFDISK**, die Anwendung muss nicht den Druckauftrag abzubrechen. Ist dies nicht der Fall ist, er muss liefern, den Druck-Manager durch Aufrufen der **PeekMessage** oder **GetMessage** Windows-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert der Funktion Abort-Handler ist ungleich NULL, wenn der Druckauftrag ist, um den Vorgang fortzusetzen, und 0, wenn er abgebrochen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Name muss exportiert werden, wie im Abschnitt Hinweise unter [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](structures-styles-callbacks-and-message-maps.md)
 [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)
 [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc)
 [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring)



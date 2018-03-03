---
title: "Von MFC verwendete Rückruffunktionen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adcde434c12c11c1df7fc1367b658114f874b3c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="callback-functions-used-by-mfc"></a>Von MFC verwendete Rückruffunktionen
Drei Fehlerrückruf-Funktionen werden in der Microsoft Foundation Class-Bibliothek angezeigt. Diese Rückruffunktionen übergeben werden, um [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring), und [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc). Beachten Sie, dass alle Rückruffunktionen MFC-Ausnahmen abfangen müssen, vor der Rückgabe an Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht aus. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  

|name||  
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
 Verweist auf eine [LOGPEN](../../mfc/reference/logpen-structure.md) oder [LOGBRUSH](../../mfc/reference/logbrush-structure.md) Datenstruktur, die Informationen zu den logischen Attributen des Objekts enthält.  
  
 `lpData`  
 Verweist auf die von der Anwendung bereitgestellten übergeben, um die `EnumObjects` Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Rückruffunktion gibt eine `int`. Der Wert dieser Rendite ist benutzerdefiniert. Wenn die Rückruffunktion 0 (null) zurückgibt `EnumObjects` Enumeration vorzeitig beendet.  
  
### <a name="remarks"></a>Hinweise  
 Der tatsächliche Name muss exportiert werden.  
  
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
 Bezeichnet einen Speichergerätekontext mit einer Bitmap mit mindestens der Breite und Höhe gemäß `nWidth` und `nHeight` auf `GrayString`.  
  
 `lpData`  
 Zeigt auf die zu zeichnende Zeichenfolge.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen ausgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Rückgabewert der Rückruffunktion muss **"true"** zum Erfolg; andernfalls handelt es sich **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückruffunktion (*OutputFunc*) muss ein Bild im Verhältnis die Koordinaten (0,0) zeichnen statt (*x*, *y*).  

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
 Gibt an, ob ein Fehler aufgetreten ist. Es ist 0, wenn kein Fehler aufgetreten ist. Es ist **SP_OUTOFDISK** , wenn der Druck-Manager derzeit kein Speicherplatz mehr ist und mehr Speicherplatz Verfügung gestellt zur, wenn die Anwendung wartet. Wenn `code` ist **SP_OUTOFDISK**, die Anwendung muss sich nicht in den Druckauftrag abbrechen. Wenn dies nicht der Fall sein, es muss Zurückhalten Druck-Manager durch Aufrufen der **PeekMessage** oder **GetMessage** Windows-Funktion.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert der Funktion Abort-Handler ist ungleich NULL, wenn der Druckauftrag wird fortgesetzt, und 0, wenn sie abgebrochen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der tatsächliche Name muss exportiert werden, wie im Abschnitt "Hinweise" beschriebenen [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc).  
 
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](structures-styles-callbacks-and-message-maps.md) [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects) [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc) [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring)


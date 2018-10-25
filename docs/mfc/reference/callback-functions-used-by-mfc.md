---
title: Von MFC verwendete Rückruffunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3093ca60b222512e517400f478fc9d635a6f867
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073772"
---
# <a name="callback-functions-used-by-mfc"></a>Von MFC verwendete Rückruffunktionen

Drei Rückruffunktionen werden in der Microsoft Foundation Class-Bibliothek angezeigt. An dieser Rückruffunktionen übergeben werden [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring), und [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc). Beachten Sie, dass alle Rückruffunktionen MFC-Ausnahmen abfangen müssen, bevor an Windows, zurückgegeben werden, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht an. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

|name||
|----------|-----------------|
|[Rückruffunktion für CDC::EnumObjects](#enum_objects)||
|[Rückruffunktion für CDC::GrayString](#graystring)||
|[Rückruffunktion für CDC::SetAbortProc](#setabortproc)||

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="enum_objects"></a> Rückruffunktion für CDC:: EnumObjects

Die *ObjectFunc* Name ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.

### <a name="syntax"></a>Syntax

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parameter

*lpszLogObject*<br/>
Verweist auf eine [LOGPEN](../../mfc/reference/logpen-structure.md) oder [LOGBRUSH](../../mfc/reference/logbrush-structure.md) -Datenstruktur, die Informationen zu den logischen Attributen des Objekts enthält.

*lpData*<br/>
Verweist auf die Anwendung bereitgestellte Daten, die an die `EnumObjects` Funktion.

### <a name="return-value"></a>Rückgabewert

Die Callback-Funktion gibt ein **Int**. Der Wert von diesem Return wird vom Benutzer festgelegt. Wenn die Callback-Funktion gibt 0 (null) zurück, `EnumObjects` Enumeration frühzeitig beendet.

### <a name="remarks"></a>Hinweise

Der Name muss exportiert werden.

## <a name="graystring"></a>  Rückruffunktion für CDC:: graystring

*OutputFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellten Rückruffunktion.

### <a name="syntax"></a>Syntax

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parameter

*hDC*<br/>
Identifiziert einen Speichergerätekontext mit einer Bitmap mit mindestens der Breite und Höhe gemäß `nWidth` und `nHeight` zu `GrayString`.

*lpData*<br/>
Zeigt auf die zu zeichnende Zeichenfolge.

*nCount*<br/>
Gibt die Anzahl von Zeichen ausgegeben.

### <a name="return-value"></a>Rückgabewert

Die Callback-Funktion zurückgegebene Wert muss "true", um den Erfolg mitzuteilen, Andernfalls ist er "false".

### <a name="remarks"></a>Hinweise

Die Callback-Funktion (*OutputFunc*) müssen Zeichnen eines Bilds relativ zu den Koordinaten (0,0) statt (*x*, *y*).

## <a name="setabortproc"></a>  Rückruffunktion für CDC:: setabortproc

Der Name *AbortFunc* ist ein Platzhalter für den Namen der Anwendung bereitgestellte Funktion.

### <a name="syntax"></a>Syntax

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parameter

*hPr*<br/>
Gibt den Gerätekontext.

*Code*<br/>
Gibt an, ob ein Fehler aufgetreten ist. Es ist 0, wenn kein Fehler aufgetreten ist. Es ist SP_OUTOFDISK, wenn der Druck-Manager befindet sich derzeit nicht genügend Speicherplatz und mehr Speicherplatz zur Verfügung stehen, wenn die Anwendung wartet. Wenn *Code* SP_OUTOFDISK, wird die Anwendung muss nicht den Druckauftrag abbrechen. Wenn dies nicht der Fall ist, muss, führt dies zu den Druck-Manager durch Aufrufen der `PeekMessage` oder `GetMessage` Windows-Funktion.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert der Funktion Abort-Handler ist ungleich NULL, wenn der Druckauftrag wird, um den Vorgang fortzusetzen, und 0, wenn sie abgebrochen wird.

### <a name="remarks"></a>Hinweise

Der Name muss exportiert werden, wie beschrieben im Abschnitt "Hinweise" des [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)


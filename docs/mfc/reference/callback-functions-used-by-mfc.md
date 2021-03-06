---
title: Von MFC verwendete Rückruffunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 9e51774b2158a81fce05dc0bd27e296e4ad94faa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507702"
---
# <a name="callback-functions-used-by-mfc"></a>Von MFC verwendete Rückruffunktionen

Drei Rückruf Funktionen werden in der Microsoft Foundation Class-Bibliothek angezeigt. Diese Rückruf Funktionen werden an [CDC:: enujubjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring)und [CDC:: abtabortproc](../../mfc/reference/cdc-class.md#setabortproc)übermittelt. Beachten Sie, dass alle Rückruf Funktionen vor der Rückgabe an Windows MFC-Ausnahmen abfangen müssen, da Ausnahmen nicht über Rückruf Grenzen hinweg ausgelöst werden können. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).

|Name||
|----------|-----------------|
|[Rückruffunktion für CDC::EnumObjects](#enum_objects)||
|[Rückruffunktion für CDC::GrayString](#graystring)||
|[Rückruffunktion für CDC::SetAbortProc](#setabortproc)||

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="enum_objects"></a>Rückruffunktion für CDC:: enumujects

Der *objectfunc* -Name ist ein Platzhalter für den von der Anwendung bereitgestellten Funktionsnamen.

### <a name="syntax"></a>Syntax

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parameter

*lpszLogObject*<br/>
Verweist auf eine [logpen](/windows/win32/api/Wingdi/ns-wingdi-logpen) -oder [logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush) -Datenstruktur, die Informationen zu den logischen Attributen des-Objekts enthält.

*lpData*<br/>
Verweist auf die von der Anwendung bereitgestellten Daten, `EnumObjects` die an die Funktion übergeben werden.

### <a name="return-value"></a>Rückgabewert

Die Rückruffunktion gibt einen **int**-Wert zurück. Der Wert dieser Rückgabe ist Benutzer definiert. Wenn die Rückruffunktion 0 zurückgibt `EnumObjects` , hält die Enumeration frühzeitig an.

### <a name="remarks"></a>Hinweise

Der tatsächliche Name muss exportiert werden.

## <a name="graystring"></a>Rückruffunktion für CDC:: graystring

*OutputFunc* ist ein Platzhalter für den von der Anwendung bereitgestellten Rückruf Funktionsnamen.

### <a name="syntax"></a>Syntax

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parameter

*hDC*<br/>
Identifiziert einen Speichergeräte Kontext mit einer Bitmap von mindestens der von `nWidth` `GrayString`und `nHeight` angegebenen Breite und Höhe.

*lpData*<br/>
Zeigt auf die zu zeichnende Zeichenfolge.

*nCount*<br/>
Gibt die Anzahl von Zeichen an, die ausgegeben werden sollen.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert der Rückruffunktion muss "true" sein, um den Erfolg anzugeben. Andernfalls ist Sie false.

### <a name="remarks"></a>Hinweise

Die Rückruffunktion (*OutputFunc*) muss ein Bild relativ zu den Koordinaten (0, 0) anstelle von (*x*, *y*) zeichnen.

## <a name="setabortproc"></a>Rückruffunktion für CDC:: abtabortproc

Der Name *abortfunc* ist ein Platzhalter für den von der Anwendung bereitgestellten Funktionsnamen.

### <a name="syntax"></a>Syntax

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parameter

*hPr*<br/>
Identifiziert den Gerätekontext.

*Code*<br/>
Gibt an, ob ein Fehler aufgetreten ist. Der Wert ist 0, wenn kein Fehler aufgetreten ist. Dies ist SP_OUTOFDISK, wenn der Druck-Manager zurzeit nicht über genügend Speicherplatz verfügt und bei der Wartezeit der Anwendung mehr Speicherplatz zur Verfügung steht. Wenn *Code* SP_OUTOFDISK ist, muss die Anwendung den Druckauftrag nicht abbrechen. Wenn dies nicht der Fall ist, muss Sie dem Druck-Manager durch Aufrufen `PeekMessage` der `GetMessage` -oder der Windows-Funktion zurückzugeben.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert der Abort-Handler-Funktion ist ungleich 0 (null), wenn der Druckauftrag fortgesetzt werden soll, und 0, wenn er abgebrochen wird.

### <a name="remarks"></a>Hinweise

Der tatsächliche Name muss exportiert werden, wie im Abschnitt "Hinweise" von [CDC:: abtabortproc](../../mfc/reference/cdc-class.md#setabortproc)beschrieben.

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)

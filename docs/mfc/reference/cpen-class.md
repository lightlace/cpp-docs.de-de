---
title: CPen-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: 952d270acd47b5834a06b731f7875ea2efdd4695
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502950"
---
# <a name="cpen-class"></a>CPen-Klasse

Kapselt einen Stift der Windows GDI (Graphics Device Interface).

## <a name="syntax"></a>Syntax

```
class CPen : public CGdiObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPen:: CPen](#cpen)|Erstellt ein `CPen`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPen:: kreatepen](#createpen)|Erstellt einen logischen, kosmetischen oder geometrischen Stift mit dem angegebenen Stil, der angegebenen Breite und den angegebenen Pinsel Attributen und fügt `CPen` ihn an das-Objekt an.|
|[CPen::CreatePenIndirect](#createpenindirect)|Erstellt einen Stift mit dem Stil, der Breite und der Farbe, der in einer [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) -Struktur angegeben ist, `CPen` und fügt ihn an das-Objekt an.|
|[CPen:: FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CPen` -Objekt zurück, wenn ein Windows-HPEN angegeben ist.|
|[CPen::GetExtLogPen](#getextlogpen)|Ruft eine zugrunde liegende [extlogpen](/windows/win32/api/wingdi/ns-wingdi-extlogpen) -Struktur ab.|
|[CPen::GetLogPen](#getlogpen)|Ruft eine zugrunde liegende [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) -Struktur ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CPen:: Operator HPEN](#operator_hpen)|Gibt das an das `CPen` -Objekt angefügte Windows-Handle zurück.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zum Verwenden von `CPen`finden Sie unter [Graphic Objects](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cpen"></a>CPen:: CPen

Erstellt ein `CPen`-Objekt.

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Parameter

*nPenStyle*<br/>
Gibt den Stift Stil an. Dieser Parameter in der ersten Version des Konstruktors kann einen der folgenden Werte aufweisen:

- PS_SOLID erstellt einen voll soliden Stift.

- PS_DASH erstellt einen gestrichelten Stift. Nur gültig, wenn die Stift Breite in Geräte Einheiten 1 oder kleiner ist.

- PS_DOT erstellt einen gepunkteten Stift. Nur gültig, wenn die Stift Breite in Geräte Einheiten 1 oder kleiner ist.

- PS_DASHDOT erstellt einen Stift mit abwechselnden Bindestrichen und Punkten. Nur gültig, wenn die Stift Breite in Geräte Einheiten 1 oder kleiner ist.

- PS_DASHDOTDOT erstellt einen Stift mit abwechselnden Bindestrichen und doppelten Punkten. Nur gültig, wenn die Stift Breite in Geräte Einheiten 1 oder kleiner ist.

- PS_NULL erstellt einen NULL-Stift.

- PS_INSIDEFRAME erstellt einen Stift, der eine Linie innerhalb des Frames geschlossener Formen zeichnet, die von den Windows-GDI-Ausgabefunktionen erzeugt werden, die ein umschließendes `Ellipse`Rechteck `Rectangle`angeben ( `Pie`z. b.,, `RoundRect`, und `Chord`).Member-Funktionen). Wenn dieser Stil mit Windows-GDI-Ausgabefunktionen verwendet wird, die kein umschließendes Rechteck angeben (z. `LineTo` b. die Member-Funktion), wird der Zeichnungs Bereich des Stifts nicht durch einen Frame beschränkt.

Die zweite Version des `CPen` Konstruktors gibt eine Kombination aus Typ, Stil, EndCap und Joinattributen an. Die Werte aus jeder Kategorie sollten mithilfe des bitweisen OR-Operators (&#124;) kombiniert werden. Der Stift-Typ kann einen der folgenden Werte aufweisen:

- PS_GEOMETRIC erstellt einen geometrischen Stift.

- PS_COSMETIC erstellt einen kosmetischen Stift.

   Die zweite Version des `CPen` Konstruktors fügt die folgenden Pen-Stile für *npenstyle*hinzu:

- PS_ALTERNATE erstellt einen Stift, mit dem jedes andere Pixel festgelegt wird. (Dieser Stil ist nur für kosmetische Stifte anwendbar.)

- PS_USERSTYLE erstellt einen Stift, der ein vom Benutzer bereitgestelltes Formatvorlagen Array verwendet.

   Die endbegrenzung kann einen der folgenden Werte aufweisen:

- PS_ENDCAP_ROUND ENDCAPS sind Round.

- PS_ENDCAP_SQUARE Ende der Obergrenzen sind quadratisch.

- PS_ENDCAP_FLAT ENDCAPS sind flach.

   Der Join kann einen der folgenden Werte aufweisen:

- PS_JOIN_BEVEL Joins werden gevelht.

- PS_JOIN_MITER Joins werden falsch verarbeitet, wenn Sie sich innerhalb des aktuellen Limits befinden, das durch die [setmiterlimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) -Funktion festgelegt wird. Wenn der Join diesen Grenzwert überschreitet, wird er gevelht.

- PS_JOIN_ROUND Joins sind Round.

*nWidth*<br/>
Gibt die Breite des Stifts an.

- Wenn dieser Wert für die erste Version des Konstruktors 0 ist, ist die Breite in den Geräte Einheiten immer 1 Pixel, unabhängig vom Kartenmodus.

- Bei der zweiten Version des Konstruktors wird die Breite in logischen Einheiten angegeben, wenn *nstistyle* PS_GEOMETRIC ist. Wenn *nstistyle* auf PS_COSMETIC festgelegt ist, muss die Breite auf 1 festgelegt werden.

*crColor*<br/>
Enthält eine RGB-Farbe für den Stift.

*pLogBrush*<br/>
Verweist auf eine `LOGBRUSH` -Struktur. Wenn *npenstyle* auf PS_COSMETIC festgelegt ist, gibt der *lbcolor* - `LOGBRUSH` Member der-Struktur die Farbe des Stifts an, und der *lbstyle* -Member der `LOGBRUSH` -Struktur muss auf BS_SOLID festgelegt werden. Wenn *npenstyle* auf PS_GEOMETRIC festgelegt ist, müssen alle Member zum Angeben der Pinsel Attribute des Stifts verwendet werden.

*nStyleCount*<br/>
Gibt die Länge des *lpstyle* -Arrays in Double Word-Einheiten an. Dieser Wert muss 0 (null) lauten, wenn *nstistyle* nicht PS_USERSTYLE ist.

*lpStyle*<br/>
Verweist auf ein Array von Double Word-Werten. Der erste Wert gibt die Länge des ersten Bindestrichs in einem benutzerdefinierten Stil an, der zweite Wert gibt die Länge des ersten leer Zeichens an usw. Dieser Zeiger muss NULL sein, wenn *nstistyle* nicht PS_USERSTYLE ist.

### <a name="remarks"></a>Hinweise

Wenn Sie den-Konstruktor ohne Argumente verwenden `CPen` , müssen Sie das resultierende-Objekt mit den `CreatePen`-, `CreatePenIndirect`-oder `CreateStockObject` -Element Funktionen initialisieren.

Wenn Sie den Konstruktor verwenden, der Argumente annimmt, ist keine weitere Initialisierung erforderlich. Der Konstruktor mit Argumenten kann eine Ausnahme auslösen, wenn Fehler auftreten, während der Konstruktor ohne Argumente immer erfolgreich ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

##  <a name="createpen"></a>CPen:: kreatepen

Erstellt einen logischen, kosmetischen oder geometrischen Stift mit dem angegebenen Stil, der angegebenen Breite und den angegebenen Pinsel Attributen und fügt `CPen` ihn an das-Objekt an.

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>Parameter

*nPenStyle*<br/>
Gibt den Stil für den Stift an. Eine Liste möglicher Werte finden Sie unter dem *npenstyle* -Parameter im [CPen](#cpen) -Konstruktor.

*nWidth*<br/>
Gibt die Breite des Stifts an.

- Wenn dieser Wert für die `CreatePen`erste Version von 0 ist, ist die Breite in den Geräte Einheiten immer 1 Pixel, unabhängig vom Kartenmodus.

- Bei der zweiten Version von `CreatePen`wird die Breite in logischen Einheiten angegeben, wenn *nstistyle* den Wert PS_GEOMETRIC hat. Wenn *nstistyle* auf PS_COSMETIC festgelegt ist, muss die Breite auf 1 festgelegt werden.

*crColor*<br/>
Enthält eine RGB-Farbe für den Stift.

*pLogBrush*<br/>
Verweist auf eine [logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush) -Struktur. Wenn *npenstyle* auf PS_COSMETIC festgelegt `lbColor` ist, gibt `LOGBRUSH` der-Member der-Struktur die Farbe des Stifts an, und `LOGBRUSH` der *lbstyle* -Member der-Struktur muss auf BS_SOLID festgelegt werden. Wenn npenstyle auf PS_GEOMETRIC festgelegt ist, müssen alle Member zum Angeben der Pinsel Attribute des Stifts verwendet werden.

*nStyleCount*<br/>
Gibt die Länge des *lpstyle* -Arrays in Double Word-Einheiten an. Dieser Wert muss 0 (null) lauten, wenn *nstistyle* nicht PS_USERSTYLE ist.

*lpStyle*<br/>
Verweist auf ein Array von Double Word-Werten. Der erste Wert gibt die Länge des ersten Bindestrichs in einem benutzerdefinierten Stil an, der zweite Wert gibt die Länge des ersten leer Zeichens an usw. Dieser Zeiger muss NULL sein, wenn *nstistyle* nicht PS_USERSTYLE ist.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich, oder 0 (null), wenn die Methode fehlschlägt.

### <a name="remarks"></a>Hinweise

Die erste Version von `CreatePen` Initialisiert einen Stift mit dem angegebenen Stil, der angegebenen Breite und der angegebenen Farbe. Der Stift kann anschließend als aktueller Stift für beliebige Geräte Kontexte ausgewählt werden.

Für Stifte mit einer Breite von mehr als 1 Pixel sollte immer der Stil PS_NULL, PS_SOLID oder PS_INSIDEFRAME vorhanden sein.

Wenn ein Stift den PS_INSIDEFRAME-Stil und eine Farbe hat, die nicht mit einer Farbe in der logischen Farbtabelle identisch ist, wird der Stift mit einer Dithering-Farbe gezeichnet. Der PS_SOLID Pen-Stil kann nicht verwendet werden, um einen Stift mit einer Dithering-Farbe zu erstellen. Der Style PS_INSIDEFRAME ist mit PS_SOLID identisch, wenn die Stift Breite kleiner oder gleich 1 ist.

Die zweite Version von `CreatePen` Initialisiert einen logischen, kosmetischen oder geometrischen Stift, der über die angegebenen Attribute für Stil, Breite und Pinsel verfügt. Die Breite eines kosmetischen Stifts ist immer 1. die Breite eines geometrischen Stifts wird immer in Welteinheiten angegeben. Nachdem eine Anwendung einen logischen Stift erstellt hat, kann Sie diesen Stift in einen Gerätekontext auswählen, indem die [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) -Funktion aufgerufen wird. Nachdem ein Stift in einen Gerätekontext ausgewählt wurde, kann er zum Zeichnen von Linien und Kurven verwendet werden.

- Wenn *ntzstyle* "PS_COSMETIC" und "PS_USERSTYLE" ist, geben die Einträge im *lpstyle* -Array Längen von Bindestrichen und Leerzeichen in Stil Einheiten an. Eine Format Einheit wird von dem Gerät definiert, in dem der Stift zum Zeichnen einer Linie verwendet wird.

- Wenn *ntzstyle* auf PS_GEOMETRIC und PS_USERSTYLE festgelegt ist, geben die Einträge im *lpstyle* -Array Längen von Bindestrichen und Leerzeichen in logischen Einheiten an.

- Wenn *nstistyle* auf PS_ALTERNATE festgelegt ist, wird die Stil Einheit ignoriert, und jedes andere Pixel wird festgelegt.

Wenn eine Anwendung keinen bestimmten Stift mehr benötigt, sollte Sie die [CGdiObject::D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) -Member-Funktion oder das `CPen` Objekt zerstören, damit die Ressource nicht mehr verwendet wird. Eine Anwendung sollte keinen Stift löschen, wenn der Stift in einem Gerätekontext ausgewählt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

##  <a name="createpenindirect"></a>CPen:: kreatepkoindirekte

Initialisiert einen Stift, der den Stil, die Breite und die Farbe aufweist, die in der Struktur angegeben sind, auf die von *lplogpen*verwiesen wird.

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>Parameter

*lpLogPen*<br/>
Verweist auf die Windows- [logpen](/windows/win32/api/Wingdi/ns-wingdi-logpen) -Struktur, die Informationen über den Stift enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Für Stifte mit einer Breite von mehr als 1 Pixel sollte immer der Stil PS_NULL, PS_SOLID oder PS_INSIDEFRAME vorhanden sein.

Wenn ein Stift den PS_INSIDEFRAME-Stil und eine Farbe hat, die nicht mit einer Farbe in der logischen Farbtabelle identisch ist, wird der Stift mit einer Dithering-Farbe gezeichnet. Der PS_INSIDEFRAME-Stil ist identisch mit PS_SOLID, wenn die Stift Breite kleiner oder gleich 1 ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

##  <a name="fromhandle"></a>CPen:: FromHandle

Gibt einen Zeiger auf ein `CPen` -Objekt zurück, das ein Handle für ein Windows GDI-Stift Objekt erhält.

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>Parameter

*HPEN*<br/>
`HPEN`Handle für Windows-GDI-Stift.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CPen` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn ein `CPen`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CPen`-Objekt erstellt und angefügt. Dieses temporäre `CPen` Objekt ist nur gültig, bis das nächste Mal die Leerlaufzeit der Anwendung in der Ereignisschleife liegt. zu diesem Zeitpunkt werden alle temporären Grafik Objekte gelöscht. Das heißt, dass das temporäre Objekt nur während der Verarbeitung einer Fenster Nachricht gültig ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

##  <a name="getextlogpen"></a>CPen:: getextlogpen

Ruft eine `EXTLOGPEN` zugrunde liegende-Struktur ab.

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>Parameter

*pLogPen*<br/>
Verweist auf eine [extlogpen](/windows/win32/api/wingdi/ns-wingdi-extlogpen) -Struktur, die Informationen über den Stift enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die `EXTLOGPEN` -Struktur definiert den Stil, die Breite und die Pinsel Attribute eines Stifts. Beispielsweise wird aufgerufen `GetExtLogPen` , um den jeweiligen Stil eines Stifts abzugleichen.

Weitere Informationen zu Stift Attributen finden Sie in den folgenden Themen des Windows SDK:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [Extkreatepen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird das `GetExtLogPen` Aufrufen von zum Abrufen von Stift Attributen veranschaulicht. Anschließend wird ein neuer, kosmetischer Stift mit der gleichen Farbe erstellt.

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

##  <a name="getlogpen"></a>CPen:: getlogpen

Ruft eine `LOGPEN` zugrunde liegende-Struktur ab.

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>Parameter

*pLogPen*<br/>
Verweist auf eine [logpen](/windows/win32/api/wingdi/ns-wingdi-logpen) -Struktur, die Informationen über den Stift enthalten soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die `LOGPEN` -Struktur definiert den Stil, die Farbe und das Muster eines Stifts.

Beispielsweise wird aufgerufen `GetLogPen` , um eine Entsprechung für die jeweilige Art von Stift zu finden.

Weitere Informationen zu Stift Attributen finden Sie in den folgenden Themen des Windows SDK:

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht das `GetLogPen` Aufrufen von zum Abrufen eines Stift Zeichens und das anschließende Erstellen eines neuen, voll tonstifts mit der gleichen Farbe.

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

##  <a name="operator_hpen"></a>CPen:: Operator HPEN

Ruft das angefügte Windows-GDI- `CPen` Handle des-Objekts ab.

```
operator HPEN() const;
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Handle für das von dem `CPen` -Objekt dargestellte Windows-GDI-Objekt, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Typumwandlungs Operator, der die direkte Verwendung eines HPEN-Objekts unterstützt.

Weitere Informationen zum Verwenden von Grafikobjekten finden Sie im Artikel [Graphic Objects](/windows/win32/gdi/graphic-objects) in Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>Siehe auch

[CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CBrush-Klasse](../../mfc/reference/cbrush-class.md)

---
title: CPen-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17337239a3a58a0283fc96eadcd4417c3d5c69b0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079589"
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
|[CPen::CPen](#cpen)|Erstellt ein `CPen`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Erstellt einen logischen kosmetischen oder geometrischen Stift mit der angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Erstellt einen Stift mit der Art, Breite und Farbe eine [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) Struktur, und fügt es der `CPen` Objekt.|  
|[CPen::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CPen` Objekts, wenn Sie einen gegebenen `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Ruft eine [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) zugrunde liegende Struktur.|  
|[CPen::GetLogPen](#getlogpen)|Ruft eine [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) zugrunde liegende Struktur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Gibt die Windows-Handle an der die `CPen` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verwendung von `CPen`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cpen"></a>  CPen::CPen  
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
 *nPenStyle*  
 Gibt die Art der Stift. Dieser Parameter in der ersten Version des Konstruktors kann einen der folgenden Werte sein:  
  
- **PS_SOLID** eine durchgehend erstellt.  
  
- **PS_DASH** eine gestrichelt erstellt. Nur gültig, wenn die Stiftbreite 1 oder weniger im Gerät Einheiten ist.  
  
- **PS_DOT** erstellt eine gepunktet. Nur gültig, wenn die Stiftbreite 1 oder weniger im Gerät Einheiten ist.  
  
- **PS_DASHDOT** erstellt einen Stift mit abwechselnden Striche und Punkte enthalten. Nur gültig, wenn die Stiftbreite 1 oder weniger im Gerät Einheiten ist.  
  
- **PS_DASHDOTDOT** erstellt einen Stift mit abwechselnden Striche und doppelte Punkte. Nur gültig, wenn die Stiftbreite 1 oder weniger im Gerät Einheiten ist.  
  
- **PS_NULL** erstellt einen null-Stift.  
  
- **PS_INSIDEFRAME** erstellt einen Stift, der zeichnet eine verbindende Linie im Rahmen von geschlossene Formen erzeugt, die von den Funktionen der Windows-GDI-Ausgabe, die ein umschließendes Rechteck angeben (z. B. die `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, und `Chord` Memberfunktionen). Bei Verendung dieses Format mit Funktionen von Windows-GDI-Ausgabe, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Memberfunktion), der Zeichnungsbereich des Stifts wird nicht von einem Frame beschränkt.  
  
 Die zweite Version der `CPen` Konstruktor gibt eine Kombination von Typ, Stil Linienende und Join-Attribute. Die Werte aus jeder Kategorie mit dem bitweisen OR-Operator kombiniert werden soll (&#124;). Der Stifttyp ist einer der folgenden Werte möglich:  
  
- **PS_GEOMETRIC** erstellt einen geometrischen Stift.  
  
- **PS_COSMETIC** erstellt einen optische Stift.  
  
     Die zweite Version der `CPen` Konstruktor fügt die folgenden Stift Formate für *nPenStyle*:  
  
- **PS_ALTERNATE** erstellt einen Stift, der alle anderen Pixel festlegt. (Dieser Stil gilt nur für kosmetische Stifte).  
  
- **PS_USERSTYLE** erstellt einen Stift, der ein vom Benutzer bereitgestellten Styling-Array verwendet.  
  
     Das Linienende ist einer der folgenden Werte möglich:  
  
- **PS_ENDCAP_ROUND** Linienenden round sind.  
  
- **PS_ENDCAP_SQUARE** Linienenden quadratische sind.  
  
- **PS_ENDCAP_FLAT** Linienenden sind Flatfile.  
  
     Der Join kann einen der folgenden Werte sein:  
  
- **PS_JOIN_BEVEL** Joins abgeschrägt sind.  
  
- **PS_JOIN_MITER** Joins sind werden in das aktuelle Limit Gehrung die [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) Funktion. Wenn die Verknüpfung dieses Limit überschreitet, wird es abgeschrägt.  
  
- **PS_JOIN_ROUND** Joins sind runden.  
  
 *nWidth*  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des Konstruktors Wenn dieser Wert 0 ist, ist die Breite in Geräteeinheiten immer 1 Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version des Konstruktors Wenn *nPenStyle* ist **PS_GEOMETRIC**, erhält die Breite in logischen Einheiten. Wenn *nPenStyle* ist **PS_COSMETIC**, der die Breite muss auf 1 festgelegt werden.  
  
 *crColor*  
 Enthält eine RGB-Farbe für den Stift an.  
  
 *pLogBrush*  
 Verweist auf eine `LOGBRUSH` Struktur. Wenn *nPenStyle* ist **PS_COSMETIC**, *LbColor* Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und *LbStyle*Mitglied der `LOGBRUSH` Struktur muss festgelegt werden, um **BS_SOLID**. Wenn *nPenStyle* ist **PS_GEOMETRIC**, müssen alle Elemente an, die Pinsel-Attribute des Stifts verwendet werden.  
  
 *nStyleCount*  
 Gibt die Länge in Einheiten Doppelwort, der die *LpStyle* Array. Dieser Wert muss NULL, wenn sein *nPenStyle* nicht **PS_USERSTYLE**.  
  
 *lpStyle*  
 Verweist auf ein Array von Werten Doppelwort. Der erste Wert gibt die Länge des ersten Bindestrich in einem benutzerdefinierten Format, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss **NULL** Wenn *nPenStyle* nicht **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie initialisieren, das resultierende `CPen` -Objekt mit den `CreatePen`, `CreatePenIndirect`, oder `CreateStockObject` Memberfunktionen.  
  
 Wenn Sie den Konstruktor, der Argumente akzeptiert verwenden, ist keine weitere Initialisierung erforderlich. Der Konstruktor mit Argumenten kann Fehler auftreten, während der Konstruktor ohne Argumente immer erfolgreich sein wird, eine Ausnahme ausgelöst.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>  CPen::CreatePen  
 Erstellt einen logischen kosmetischen oder geometrischen Stift mit der angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.  
  
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
 *nPenStyle*  
 Gibt den Stil für den Stift. Eine Liste der möglichen Werte finden Sie unter der *nPenStyle* Parameter in der [CPen](#cpen) Konstruktor.  
  
 *nWidth*  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des `CreatePen`, wenn dieser Wert 0 ist, die Breite in Geräteeinheiten ist immer 1 Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version der `CreatePen`, wenn *nPenStyle* ist **PS_GEOMETRIC**, erhält die Breite in logischen Einheiten. Wenn *nPenStyle* ist **PS_COSMETIC**, der die Breite muss auf 1 festgelegt werden.  
  
 *crColor*  
 Enthält eine RGB-Farbe für den Stift an.  
  
 *pLogBrush*  
 Verweist auf eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur. Wenn *nPenStyle* ist **PS_COSMETIC**, **LbColor** Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und *LbStyle*Mitglied der `LOGBRUSH` Struktur muss festgelegt werden, um **BS_SOLID**. Wenn **nPenStyle** ist **PS_GEOMETRIC**, müssen alle Elemente an, die Pinsel-Attribute des Stifts verwendet werden.  
  
 *nStyleCount*  
 Gibt die Länge in Einheiten Doppelwort, der die *LpStyle* Array. Dieser Wert muss NULL, wenn sein *nPenStyle* nicht **PS_USERSTYLE**.  
  
 *lpStyle*  
 Verweist auf ein Array von Werten Doppelwort. Der erste Wert gibt die Länge des ersten Bindestrich in einem benutzerdefinierten Format, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss **NULL** Wenn *nPenStyle* nicht **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, oder 0 (null), wenn die Methode fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version des `CreatePen` ein Stiftes mit der angegebenen Art, Breite und Farbe initialisiert. Der Tablettstift kann anschließend als den aktuellen Stift für alle Gerätekontext ausgewählt werden.  
  
 Stifte, die eine Breite größer als 1 Pixel immer entweder haben sollen, die **PS_NULL**, **PS_SOLID**, oder **PS_INSIDEFRAME** Stil.  
  
 Verfügt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift mit einem Ditheringfarbe gezeichnet wird. Die **PS_SOLID** Stiftstil kann nicht verwendet werden, um mit einer Farbe ein Stiftes erstellen. Das Format **PS_INSIDEFRAME** ist identisch mit **PS_SOLID** , wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
 Die zweite Version der `CreatePen` einen logischen kosmetischen oder geometrischen Stift, der dem angegebenen Stil, Breite und Pinsel Attribute initialisiert. Die Breite eines Stiftes kosmetische ist immer 1. eine geometrische Stiftbreite wird immer im globalen Einheiten angegeben. Nachdem eine Anwendung einen logischen Stift erstellt hat, können sie den Stift einen Gerätekontext auswählen, durch Aufrufen der [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) Funktion. Nachdem ein Stift einen Gerätekontext ausgewählt ist, können sie zum Zeichnen von Linien und Kurven verwendet werden.  
  
-   Wenn *nPenStyle* ist **PS_COSMETIC** und **PS_USERSTYLE**, die Einträge in der *LpStyle* Array geben die Längen der Striche und Zwischenräume in Stil-Einheiten. Eine Einheit Stil wird vom Gerät definiert, in dem der Stift verwendet wird, um eine Linie zu zeichnen.  
  
-   Wenn *nPenStyle* ist **PS_GEOMETRIC** und **PS_USERSTYLE**, die Einträge in der *LpStyle* Array geben die Längen der Striche und Zwischenräume in logische Einheiten.  
  
-   Wenn *nPenStyle* ist **PS_ALTERNATE**, die Formatvorlage Einheit wird ignoriert, und alle anderen Pixel festgelegt ist.  
  
 Wenn eine Anwendung einen bestimmten Stift nicht mehr erforderlich ist, rufen sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion oder sogar zerstört werden die `CPen` Objekt, damit die Ressource nicht mehr verwendet wird. Eine Anwendung sollte ein Stiftes nicht löschen, wenn der Stift in einem Gerätekontext ausgewählt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect  
 Initialisiert einen Stift, der die Art, Breite und Farbe in der Struktur verweist hat *LpLogPen*.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *lpLogPen*  
 Verweist auf den Windows [LOGPEN](../../mfc/reference/logpen-structure.md) -Struktur, die Informationen zu den Stift enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Stifte, die eine Breite größer als 1 Pixel immer entweder haben sollen, die **PS_NULL**, **PS_SOLID**, oder **PS_INSIDEFRAME** Stil.  
  
 Verfügt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift mit einem Ditheringfarbe gezeichnet wird. Die **PS_INSIDEFRAME** Format ist identisch mit **PS_SOLID** , wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>  CPen::FromHandle  
 Gibt einen Zeiger auf eine `CPen` Objekt ein Handle mit einem Windows-GDI-Pen-Objekt.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Parameter  
 *hPen*  
 `HPEN` Handle für eine Windows-GDI-Stift.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPen` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CPen`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CPen`-Objekt erstellt und angefügt. Dieser temporäre `CPen` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu dem alle temporären Grafik Zeit Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht von einem Fenster gültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>  CPen::GetExtLogPen  
 Ruft eine **EXTLOGPEN** zugrunde liegende Struktur.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogPen*  
 Verweist auf ein [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) -Struktur, die Informationen zu den Stift enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **EXTLOGPEN** Struktur definiert die Art, Breite und Pinsel Attribute eines Stiftes. Rufen Sie z. B. `GetExtLogPen` mit bestimmten nachrichtenstil eines Stiftes übereinstimmen.  
  
 Finden Sie unter den folgenden Themen im Windows SDK für Informationen über Attribute:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetExtLogPen` zum Abrufen eines Stiftes Attribute, und erstellen Sie einen neue kosmetischen Stift mit der gleichen Farbe.  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>  CPen::GetLogPen  
 Ruft eine `LOGPEN` zugrunde liegende Struktur.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogPen*  
 Verweist auf eine [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) Struktur, um Informationen zu den Stift enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `LOGPEN` Struktur definiert die Formatvorlage, die Farbe und die Muster eines Stiftes.  
  
 Rufen Sie z. B. `GetLogPen` entsprechend der bestimmten nachrichtenstil Stift.  
  
 Finden Sie unter den folgenden Themen im Windows SDK für Informationen über Attribute:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetLogPen` ein Stift Zeichen abrufen und erstellen Sie einen neue einfarbigen Stift mit der gleichen Farbe.  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>  CPen::operator HPEN  
 Ruft das angefügte Windows-GDI-Handle von der `CPen` Objekt.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPen` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HPEN` Objekt.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBrush-Klasse](../../mfc/reference/cbrush-class.md)

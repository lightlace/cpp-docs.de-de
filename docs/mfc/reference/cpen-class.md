---
title: CPen-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 60fb1c219068cc0c59f908688ea5c471946458ad
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204140"
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
|[CPen::CreatePen](#createpen)|Erstellt einen logischen kosmetischer Natur oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Erstellt einen Stift mit Stil, Breite und Farbe, die im angegebenen ein [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) Struktur, und fügt es der `CPen` Objekt.|  
|[CPen::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CPen` Objekt, wenn ein Windows-HPEN angegeben.|  
|[CPen::GetExtLogPen](#getextlogpen)|Ruft eine [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) zugrunde liegende Struktur.|  
|[CPen::GetLogPen](#getlogpen)|Ruft eine [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) zugrunde liegende Struktur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Gibt zurück, das Windows-Handle, das angefügt wird, um die `CPen` Objekt.|  
  
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
 Gibt das Pen-Format. Dieser Parameter in der ersten Version des Konstruktors kann es sich um einen der folgenden Werte sein:  
  
- PS_SOLID erstellt einen soliden Stift.  
  
- PS_DASH erstellt eine gestrichelt. Nur gültig, wenn die Stiftbreite 1 oder weniger im Geräte-Einheiten beträgt.  
  
- PS_DOT erstellt eine gepunktet. Nur gültig, wenn die Stiftbreite 1 oder weniger im Geräte-Einheiten beträgt.  
  
- PS_DASHDOT erstellt, ein Stift mit abwechselnden Striche und Punkte. Nur gültig, wenn die Stiftbreite 1 oder weniger im Geräte-Einheiten beträgt.  
  
- PS_DASHDOTDOT erstellt ein Stift, mit der abwechselnden Striche und doppelte Punkte. Nur gültig, wenn die Stiftbreite 1 oder weniger im Geräte-Einheiten beträgt.  
  
- PS_NULL erstellt einen null-Stift.  
  
- PS_INSIDEFRAME erstellt ein Stift, der eine Zeile innerhalb des Rahmens der geschlossene Formen zeichnet erzeugt, durch die Windows-GDI a-Funktionen, die ein umschließendes Rechteck angeben (z. B. die `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, und `Chord`Memberfunktionen). Wenn dieses Format verwendet wird, mit den Funktionen der Windows-GDI-Ausgabe, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Member-Funktion), der Zeichnungsbereich des Stifts wird nicht von einem Frame beschränkt.  
  
 Die zweite Version der `CPen` Konstruktor gibt eine Kombination von Typ, Format, Abschlusses und Join-Attribute. Die Werte aus jeder Kategorie mit dem bitweisen OR-Operator kombiniert werden soll (&#124;). Der Stifttyp kann es sich um einen der folgenden Werte sein:  
  
- PS_GEOMETRIC erstellt einen geometrischen Stift.  
  
- PS_COSMETIC erstellt einen Stift kosmetischer Natur.  
  
     Die zweite Version der `CPen` Konstruktor fügt die folgenden Pen-Formate für *nPenStyle*:  
  
- PS_ALTERNATE erstellt einen Stift, der alle anderen Pixel legt diese fest. (Dieses Format gilt nur für kosmetische Stifte.)  
  
- PS_USERSTYLE erstellt ein Stift, der ein Stil-Array, das vom Benutzer verwendet.  
  
     Das Linienende ist einer der folgenden Werte möglich:  
  
- Linienenden PS_ENDCAP_ROUND sind runde.  
  
- Linienenden PS_ENDCAP_SQUARE sind Quadrat.  
  
- Linienenden PS_ENDCAP_FLAT sind flach.  
  
     Der Join kann es sich um eine der folgenden Werte sein:  
  
- PS_JOIN_BEVEL verknüpft abgeschrägt werden kann.  
  
- PS_JOIN_MITER verknüpft Gehrung werden, wenn sie in das aktuelle Limit festgelegt sind das [SetMiterLimit](/windows/desktop/api/wingdi/nf-wingdi-setmiterlimit) Funktion. Wenn der Join über diesen Grenzwert überschreitet, wird es abgeschrägt.  
  
- PS_JOIN_ROUND verknüpft sind, runden.  
  
 *nWidth*  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des Konstruktors Wenn dieser Wert 0 (null) ist die Breite in Geräteeinheiten immer 1-Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version des Konstruktors Wenn *nPenStyle* PS_GEOMETRIC, wird die Breite in logischen Einheiten angegeben wird. Wenn *nPenStyle* PS_COSMETIC, wird die Breite muss auf 1 festgelegt werden.  
  
 *crColor*  
 Enthält eine RGB-Farbe für den Stift.  
  
 *pLogBrush*  
 Verweist auf eine `LOGBRUSH` Struktur. Wenn *nPenStyle* PS_COSMETIC, ist die *LbColor* Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und der *LbStyle* Mitglied der `LOGBRUSH` Struktur muss auf BS_SOLID festgelegt werden. Wenn *nPenStyle* PS_GEOMETRIC, werden alle Elemente müssen verwendet werden, um die Attribute der Pinsel des Stifts angeben.  
  
 *nStyleCount*  
 Gibt die Länge in Einheiten von zeigt Doppelwort, das *LpStyle* Array. Dieser Wert muss NULL, wenn sein *nPenStyle* ist kein PS_USERSTYLE.  
  
 *lpStyle*  
 Zeigt auf ein Array von Werten für zeigt Doppelwort. Der erste Wert gibt die Länge des ersten Strichs eines benutzerdefinierten Formats, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss NULL sein, wenn *nPenStyle* ist kein PS_USERSTYLE.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie die resultierende initialisieren `CPen` Objekt mit der `CreatePen`, `CreatePenIndirect`, oder `CreateStockObject` Memberfunktionen.  
  
 Wenn Sie den Konstruktor, der Argumente akzeptiert verwenden, ist keine weitere Initialisierung erforderlich. Der Konstruktor mit Argumenten kann eine Ausnahme auslösen, wenn Fehler auftreten, während der Konstruktor ohne Argumente immer erfolgreich ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>  CPen::CreatePen  
 Erstellt einen logischen kosmetischer Natur oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.  
  
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
 Gibt das Format für den Stift. Eine Liste der möglichen Werte, finden Sie unter den *nPenStyle* Parameter in der [CPen](#cpen) Konstruktor.  
  
 *nWidth*  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des `CreatePen`, wenn dieser Wert 0 ist, der die Breite in Geräteeinheiten ist immer 1 Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version der `CreatePen`, wenn *nPenStyle* PS_GEOMETRIC, wird die Breite in logischen Einheiten angegeben wird. Wenn *nPenStyle* PS_COSMETIC, wird die Breite muss auf 1 festgelegt werden.  
  
 *crColor*  
 Enthält eine RGB-Farbe für den Stift.  
  
 *pLogBrush*  
 Verweist auf eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) Struktur. Wenn *nPenStyle* PS_COSMETIC, ist die `lbColor` Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und der *LbStyle* Mitglied der `LOGBRUSH` Struktur muss auf BS_ festgelegt werden SOLID. Wenn nPenStyle PS_GEOMETRIC ist, müssen alle Member zum Festlegen von Attributen des Stifts Pinsel verwendet werden.  
  
 *nStyleCount*  
 Gibt die Länge in Einheiten von zeigt Doppelwort, das *LpStyle* Array. Dieser Wert muss NULL, wenn sein *nPenStyle* ist kein PS_USERSTYLE.  
  
 *lpStyle*  
 Zeigt auf ein Array von Werten für zeigt Doppelwort. Der erste Wert gibt die Länge des ersten Strichs eines benutzerdefinierten Formats, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss NULL sein, wenn *nPenStyle* ist kein PS_USERSTYLE.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, oder NULL, wenn die Methode fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version des `CreatePen` initialisiert einen Stift, mit dem angegebenen Stil, Breite und Farbe. Der Stift kann anschließend als der aktuelle Stift für einen beliebigen Gerätekontext ausgewählt werden.  
  
 Stifte, die größer als 1-Pixel Breite aufweisen sollte immer das PS_NULL, PS_SOLID oder PS_INSIDEFRAME Format aufweisen.  
  
 Wenn ein Stift verfügt der PS_INSIDEFRAME-Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt, wird der Stift mit einer geditherte Farbe gezeichnet. Styl Stift PS_SOLID kann nicht zum Erstellen eines Stifts mit einer geditherte Farbe verwendet werden. Der Stil PS_INSIDEFRAME ist identisch mit PS_SOLID, wenn der Stift kleiner als oder gleich 1 ist.  
  
 Die zweite Version der `CreatePen` einen logischen kosmetischer Natur oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute initialisiert. Die Breite des Stifts kosmetischer Natur ist immer 1. die Breite des Stifts geometrische wird immer in globalen Einheiten angegeben werden. Nachdem eine Anwendung einen logischen Stift erstellt wurde, können sie diesem Stift einen Gerätekontext auswählen, durch den Aufruf der [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) Funktion. Nachdem ein Stift einen Gerätekontext ausgewählt wurde, kann es zum Zeichnen von Linien und Kurven verwendet werden.  
  
-   Wenn *nPenStyle* ist PS_COSMETIC und PS_USERSTYLE, die Einträge in der *LpStyle* Array angeben Längen der Striche und Zwischenräume in Style-Einheiten. Eine Einheit Stil wird vom Gerät definiert, in dem der Stift verwendet wird, um eine Linie zeichnen.  
  
-   Wenn *nPenStyle* ist PS_GEOMETRIC und PS_USERSTYLE, die Einträge in der *LpStyle* Array geben die Längen der Striche und Zwischenräume in logischen Einheiten.  
  
-   Wenn *nPenStyle* PS_ALTERNATE, die Format-Einheit wird ignoriert, und alle anderen Pixel festgelegt ist.  
  
 Wenn eine Anwendung einen bestimmten Stift nicht mehr erforderlich sind, rufen sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member Funktion oder zerstören der `CPen` Objekt, damit die Ressource nicht mehr verwendet wird. Eine Anwendung sollten einen Stift nicht löschen, wenn der Stift in einem Gerätekontext ausgewählt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect  
 Initialisiert einen Stift, der den Stil, Breite und Farbe, die in der Struktur verweist angegeben hat *LpLogPen*.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *lpLogPen*  
 Verweist auf die Windows [LOGPEN](../../mfc/reference/logpen-structure.md) -Struktur, die Informationen über das Stifteingabe enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Stifte, die größer als 1-Pixel Breite aufweisen sollte immer das PS_NULL, PS_SOLID oder PS_INSIDEFRAME Format aufweisen.  
  
 Wenn ein Stift verfügt der PS_INSIDEFRAME-Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt, wird der Stift mit einer geditherte Farbe gezeichnet. Styl PS_INSIDEFRAME ist identisch mit PS_SOLID, wenn der Stift kleiner als oder gleich 1 ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>  CPen::FromHandle  
 Gibt einen Zeiger auf eine `CPen` Objekts, dem ein Handle auf ein Windows-GDI-Pen-Objekt.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Parameter  
 *hPen*  
 `HPEN` Handle für eine Windows-GDI-Stift.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPen` -Objekt, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CPen`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CPen`-Objekt erstellt und angefügt. Diese temporären `CPen` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, an der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht für ein Fenster gültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>  CPen::GetExtLogPen  
 Ruft eine `EXTLOGPEN` zugrunde liegende Struktur.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogPen*  
 Verweist auf eine [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen) -Struktur, die Informationen über das Stifteingabe enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `EXTLOGPEN` Struktur definiert die Art, Breite und Pinsel Attribute des Stifts. Rufen Sie z. B. `GetExtLogPen` mit die bestimmte Darstellung eines Stifts übereinstimmen.  
  
 Finden Sie unter den folgenden Themen im Windows SDK Weitere Informationen zu Stift-Attributen:  
  
- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)  
  
- [EXTLOGPEN](/windows/desktop/api/wingdi/ns-wingdi-tagextlogpen)  
  
- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)  
  
- [ExtCreatePen](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetExtLogPen` dieses Stifts Attribute abrufen und erstellen Sie dann mit der gleichen Farbe eines Stifts neuen, kosmetischer Natur.  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>  CPen::GetLogPen  
 Ruft eine `LOGPEN` zugrunde liegende Struktur.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogPen*  
 Verweist auf eine [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen) Struktur, um Informationen über das Stifteingabe enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `LOGPEN` Struktur definiert, der Stil, Farbe und Muster von einem Stift.  
  
 Rufen Sie z. B. `GetLogPen` entsprechend den bestimmten Stil des Stifts.  
  
 Finden Sie unter den folgenden Themen im Windows SDK Weitere Informationen zu Stift-Attributen:  
  
- [GetObject](/windows/desktop/api/wingdi/nf-wingdi-getobject)  
  
- [LOGPEN](/windows/desktop/api/wingdi/ns-wingdi-taglogpen)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetLogPen` ein Stift Zeichen abrufen und erstellen Sie dann einen neuen, soliden Stift, mit der gleichen Farbe.  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>  CPen::operator HPEN  
 Ruft das angefügte Windows-GDI-Handle des dem `CPen` Objekt.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPen` Objekt; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung eines HPEN-Objekts unterstützt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten finden Sie im Artikel [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBrush-Klasse](../../mfc/reference/cbrush-class.md)

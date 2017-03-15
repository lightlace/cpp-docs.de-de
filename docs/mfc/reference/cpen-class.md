---
title: CPen-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- HPEN
- CPen
dev_langs:
- C++
helpviewer_keywords:
- HPEN
- CPen class
- pens, MFC
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: edea12c84a8f39161acbf367360fd86a1ff19998
ms.lasthandoff: 02/24/2017

---
# <a name="cpen-class"></a>CPen-Klasse
Kapselt einen Stift der Windows GDI (Graphics Device Interface).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|Erstellt ein `CPen`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|Erstellt einen logischen kosmetischen oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.|  
|[CPen::CreatePenIndirect](#createpenindirect)|Erstellt einen Stift mit dem Stil, Breite und Farbe einem [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) Struktur, und fügt es der `CPen` Objekt.|  
|[CPen::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CPen` bei einer Windows-Objekt `HPEN`.|  
|[CPen::GetExtLogPen](#getextlogpen)|Ruft eine [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) zugrunde liegende Struktur.|  
|[CPen::GetLogPen](#getlogpen)|Ruft eine [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) zugrunde liegende Struktur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|Gibt das Windows-Handle an der der `CPen` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verwendung von `CPen`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecpena--cpencpen"></a><a name="cpen"></a>CPen::CPen  
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
 `nPenStyle`  
 Gibt das Pen-Format. Dieser Parameter in der ersten Version des Konstruktors kann einen der folgenden Werte sein:  
  
- **PS_SOLID** eine durchgehend erstellt.  
  
- **PS_DASH** einen gestrichelten Stift erstellt. Nur gültig, wenn die Stiftbreite 1 oder weniger Gerät Einheiten beträgt.  
  
- **PS_DOT** erstellt eine gepunktet. Nur gültig, wenn die Stiftbreite 1 oder weniger Gerät Einheiten beträgt.  
  
- **PS_DASHDOT** erstellt einen Stift mit abwechselnden Striche und Punkte. Nur gültig, wenn die Stiftbreite 1 oder weniger Gerät Einheiten beträgt.  
  
- **PS_DASHDOTDOT** erstellt einen Stift mit abwechselnden Striche und doppelte Punkte. Nur gültig, wenn die Stiftbreite 1 oder weniger Gerät Einheiten beträgt.  
  
- **PS_NULL** erstellt einen Stift null.  
  
- **PS_INSIDEFRAME** erstellt einen Stift, der zeichnet eine Linie innerhalb des Rahmens der geschlossene Formen erstellt, die von den Funktionen der Windows GDI-Ausgabe, die ein umschließendes Rechteck angeben (z. B. die **Ellipse**, **Rechteck**, `RoundRect`, `Pie`, und `Chord` Memberfunktionen). Wenn dieses Format verwendet wird, mit der Windows GDI-Ausgabe-Funktionen, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Member-Funktion), die Zeichenfläche des Stifts wird nicht von einem Frame beschränkt.  
  
 Die zweite Version der `CPen` Konstruktor gibt eine Kombination von Typ, Format, Abschlusses und Join-Attribute. Die Werte aus jeder Kategorie sollte mit dem bitweisen OR-Operator (|) kombiniert werden. Der Stifttyp kann eine der folgenden Werte sein:  
  
- **PS_GEOMETRIC** erstellt einen geometrischen Stift.  
  
- **PS_COSMETIC** erstellt einen kosmetischen Stift.  
  
     Die zweite Version der `CPen` Konstruktor fügt die folgenden Stift-Formate für `nPenStyle`:  
  
- **PS_ALTERNATE** erstellt einen Stift, der alle anderen Pixel festlegt. (Dieses Format ist nur für kosmetische Stifte.)  
  
- **PS_USERSTYLE** erstellt einen Stift, der ein Stil-Array, das vom Benutzer verwendet.  
  
     Die Abschlusses kann eine der folgenden Werte sein:  
  
- **PS_ENDCAP_ROUND** Linienenden round sind.  
  
- **PS_ENDCAP_SQUARE** Linienenden quadratisch sind.  
  
- **PS_ENDCAP_FLAT** Linienenden sind flach.  
  
     Der Join ist einer der folgenden Werte möglich:  
  
- **PS_JOIN_BEVEL** Joins abgeschrägt werden.  
  
- **PS_JOIN_MITER** Joins Gehrung sind, werden innerhalb der aktuellen festlegen, indem Sie die [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) Funktion. Wenn der Join über diesen Grenzwert überschreitet, wird es abgeschrägt.  
  
- **PS_JOIN_ROUND** Joins sind runden.  
  
 `nWidth`  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des Konstruktors Wenn dieser Wert 0 ist, ist die Breite in Geräteeinheiten immer 1 Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version des Konstruktors Wenn `nPenStyle` ist **PS_GEOMETRIC**, erhält die Breite in logischen Einheiten. Wenn `nPenStyle` ist **PS_COSMETIC**, die Breite muss auf 1 festgelegt werden.  
  
 `crColor`  
 Enthält eine RGB-Farbe für den Stift.  
  
 `pLogBrush`  
 Verweist auf eine `LOGBRUSH` Struktur. Wenn `nPenStyle` ist **PS_COSMETIC**, `lbColor` Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und die `lbStyle` Mitglied der `LOGBRUSH` Struktur muss festgelegt werden, um **BS_SOLID**. Wenn `nPenStyle` ist **PS_GEOMETRIC**, müssen alle Elemente verwendet werden, um die Pinsel-Attribute des Stifts angeben.  
  
 `nStyleCount`  
 Gibt die Länge in Einheiten Doppelwort, der die `lpStyle` Array. Dieser Wert muss NULL, wenn sein `nPenStyle` nicht **PS_USERSTYLE**.  
  
 `lpStyle`  
 Zeigt auf ein Array von Doppelwort-Werten. Der erste Wert gibt die Länge des ersten Strichs in einem benutzerdefinierten Format, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss **NULL** Wenn `nPenStyle` nicht **PS_USERSTYLE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie das resultierende initialisieren `CPen` -Objekt mit den `CreatePen`, `CreatePenIndirect`, oder `CreateStockObject` Memberfunktionen.  
  
 Wenn Sie den Konstruktor, der Argumente akzeptiert verwenden, ist keine weitere Initialisierung erforderlich. Der Konstruktor mit Argumenten kann eine Ausnahme auslösen, wenn Fehler aufgetreten sind, während der Konstruktor ohne Argumente immer erfolgreich verläuft.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#99;](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="a-namecreatepena--cpencreatepen"></a><a name="createpen"></a>CPen::CreatePen  
 Erstellt einen logischen kosmetischen oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute und fügt es der `CPen` Objekt.  
  
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
 `nPenStyle`  
 Gibt den Stil für den Stift. Eine Liste der möglichen Werte finden Sie unter der `nPenStyle` -Parameter in der [CPen](#cpen) Konstruktor.  
  
 `nWidth`  
 Gibt die Breite des Stifts.  
  
-   Für die erste Version des `CreatePen`, wenn dieser Wert 0 ist, die Breite in Geräteeinheiten ist immer 1 Pixel, unabhängig von den Zuordnungsmodus.  
  
-   Für die zweite Version der `CreatePen`Wenn `nPenStyle` ist **PS_GEOMETRIC**, erhält die Breite in logischen Einheiten. Wenn `nPenStyle` ist **PS_COSMETIC**, die Breite muss auf 1 festgelegt werden.  
  
 `crColor`  
 Enthält eine RGB-Farbe für den Stift.  
  
 `pLogBrush`  
 Verweist auf eine [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) Struktur. Wenn `nPenStyle` ist **PS_COSMETIC**, **LbColor** Mitglied der `LOGBRUSH` Struktur gibt die Farbe des Stifts und die `lbStyle` Mitglied der `LOGBRUSH` Struktur muss festgelegt werden, um **BS_SOLID**. Wenn **nPenStyle** ist **PS_GEOMETRIC**, müssen alle Elemente verwendet werden, um die Pinsel-Attribute des Stifts angeben.  
  
 `nStyleCount`  
 Gibt die Länge in Einheiten Doppelwort, der die `lpStyle` Array. Dieser Wert muss NULL, wenn sein `nPenStyle` nicht **PS_USERSTYLE**.  
  
 `lpStyle`  
 Zeigt auf ein Array von Doppelwort-Werten. Der erste Wert gibt die Länge des ersten Strichs in einem benutzerdefinierten Format, der zweite Wert gibt die Länge der ersten Leerzeichen und So weiter. This-Zeiger muss **NULL** Wenn `nPenStyle` nicht **PS_USERSTYLE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, oder&0;, wenn die Methode fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version der `CreatePen` initialisiert einen Stift mit dem angegebenen Stil, Breite und Farbe. Der Stift kann anschließend als der aktuelle Stift für alle Gerätekontext ausgewählt werden.  
  
 Stifte, die eine Breite größer als 1 Pixel immer entweder haben sollen, die **PS_NULL**, **PS_SOLID**, oder **PS_INSIDEFRAME** Stil.  
  
 Besitzt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift, der mit einem geditherte Farbe gezeichnet wird. Die **PS_SOLID** Pen-Stil kann nicht verwendet werden, um einen Stift mit einer geditherte Farbe zu erstellen. Das Format **PS_INSIDEFRAME** ist identisch mit **PS_SOLID** Wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
 Die zweite Version der `CreatePen` einen logischen kosmetischen oder geometrischen Stift mit dem angegebenen Stil, Breite und Pinsel Attribute initialisiert. Eine kosmetische Stiftbreite ist immer 1. eine geometrische Stiftbreite wird immer in globalen Einheiten angegeben. Nachdem eine Anwendung einen logischen Stift erstellt hat, können sie den Stift einen Gerätekontext auswählen, durch Aufrufen der [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) Funktion. Nach ein Stift einen Gerätekontext ausgewählt ist, können sie zum Zeichnen von Linien und Kurven verwendet werden.  
  
-   Wenn `nPenStyle` ist **PS_COSMETIC** und **PS_USERSTYLE**, die Einträge in der `lpStyle` Array Längen der Striche und Zwischenräume in Style-Einheiten anzugeben. Stil Einheit ist durch das Gerät definiert, in dem der Stift, der verwendet wird, um eine Linie zu zeichnen.  
  
-   Wenn `nPenStyle` ist **PS_GEOMETRIC** und **PS_USERSTYLE**, die Einträge in der `lpStyle` Array Längen der Striche und Zwischenräume in logischen Einheiten angeben.  
  
-   Wenn `nPenStyle` ist **PS_ALTERNATE**, die Style-Einheit ignoriert, und alle anderen Pixel festgelegt ist.  
  
 Wenn eine Anwendung einen bestimmten Stift nicht mehr erforderlich sind, rufen sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) Member-Funktion oder zerstören der `CPen` Objekt, damit die Ressource nicht mehr verwendet wird. Eine Anwendung sollten einen Stift nicht löschen, wenn der Stift in einem Gerätekontext ausgewählt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#100;](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="a-namecreatepenindirecta--cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::CreatePenIndirect  
 Initialisiert einen Stift, der die Art, Breite und Farbe in der Struktur auf den `lpLogPen`.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogPen`  
 Verweist auf die Windows [LOGPEN](../../mfc/reference/logpen-structure.md) -Struktur, die Informationen zu den Stift enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Stifte, die eine Breite größer als 1 Pixel immer entweder haben sollen, die **PS_NULL**, **PS_SOLID**, oder **PS_INSIDEFRAME** Stil.  
  
 Besitzt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift, der mit einem geditherte Farbe gezeichnet wird. Die **PS_INSIDEFRAME** Format ist identisch mit **PS_SOLID** Wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#101;](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="a-namefromhandlea--cpenfromhandle"></a><a name="fromhandle"></a>CPen::FromHandle  
 Gibt einen Zeiger auf ein `CPen` Objekt ein Handle zu einem Windows-GDI-Pen-Objekt.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>Parameter  
 *hPen*  
 `HPEN`Handle für die Windows-GDI-Stift.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPen` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CPen`-Objekt nicht an das Handle angefügt ist, wird ein temporäres `CPen`-Objekt erstellt und angefügt. Dieser temporäre `CPen` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife verfügt, zu der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#105;](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="a-namegetextlogpena--cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen  
 Ruft eine **EXTLOGPEN** zugrunde liegende Struktur.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 `pLogPen`  
 Verweist auf ein [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) -Struktur, die Informationen zu den Stift enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die **EXTLOGPEN** Struktur definiert die Art, Breite und Pinsel Attribute eines Stiftes. Rufen Sie z. B. `GetExtLogPen` Format eines Stiftes übereinstimmen.  
  
 Finden Sie unter den folgenden Themen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Informationen über Attribute:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetExtLogPen` , einem Stift Attribute abzurufen, und erstellen Sie einen neue kosmetischen Stift mit der gleichen Farbe.  
  
 [!code-cpp[NVC_MFCDocView&#102;](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="a-namegetlogpena--cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen  
 Ruft eine `LOGPEN` zugrunde liegende Struktur.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>Parameter  
 `pLogPen`  
 Verweist auf eine [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) Struktur, um Informationen zu den Stift enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die `LOGPEN` Struktur definiert die Formatvorlage, Farbe und Muster von einem Stift.  
  
 Rufen Sie z. B. `GetLogPen` Format für den Stift übereinstimmen.  
  
 Finden Sie unter den folgenden Themen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Informationen über Attribute:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht den Aufruf `GetLogPen` , einem Stift Zeichen abrufen, und erstellen Sie einen neue soliden Stift mit der gleichen Farbe.  
  
 [!code-cpp[NVC_MFCDocView&#103;](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="a-nameoperatorhpena--cpenoperator-hpen"></a><a name="operator_hpen"></a>CPen::operator HPEN  
 Ruft das angefügte Windows GDI-Handle für die `CPen` Objekt.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPen` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HPEN` Objekt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#104;](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CBrush-Klasse](../../mfc/reference/cbrush-class.md)


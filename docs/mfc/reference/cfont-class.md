---
title: CFont-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFont
- AFXWIN/CFont
- AFXWIN/CFont::CFont
- AFXWIN/CFont::CreateFont
- AFXWIN/CFont::CreateFontIndirect
- AFXWIN/CFont::CreatePointFont
- AFXWIN/CFont::CreatePointFontIndirect
- AFXWIN/CFont::FromHandle
- AFXWIN/CFont::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CFont [MFC], CFont
- CFont [MFC], CreateFont
- CFont [MFC], CreateFontIndirect
- CFont [MFC], CreatePointFont
- CFont [MFC], CreatePointFontIndirect
- CFont [MFC], FromHandle
- CFont [MFC], GetLogFont
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5431461c7c2cc33131f72f059edcfbd984eae5fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cfont-class"></a>CFont-Klasse
Kapselt eine Schriftart der Windows GDI (Graphics Device Interface) und stellt Memberfunktionen zum Bearbeiten der Schriftart bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|Erstellt ein `CFont`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::](#createfont)|Initialisiert eine `CFont` mit den angegebenen Merkmalen.|  
|[CFont::CreateFontIndirect](#createfontindirect)|Initialisiert eine `CFont` mit den Merkmalen, die im angegebenen Objekt ein `LOGFONT` Struktur.|  
|[CFont::CreatePointFont](#createpointfont)|Initialisiert eine `CFont` mit der angegebenen Höhe gemessen in Zehntelsekunden einen Punkt und Schriftart.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Identisch mit `CreateFontIndirect` mit dem Unterschied, dass die Höhe der Schriftart in Zehntelsekunden ein Punkt anstatt auf logischen Einheiten gemessen wird.|  
|[CFont::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CFont` Objekts, wenn Sie einen gegebenen **HFONT**.|  
|[CFont::GetLogFont](#getlogfont)|Füllt eine `LOGFONT` mit Informationen über die logische Schriftart angefügt, um die `CFont` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|Gibt das Windows-GDI-Schriftart-Handle an die `CFont` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CFont` Objekt, das Erstellen einer `CFont` Objekt, und fügen Sie eine Windows-Schriftart an ihn mit [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), oder [CreatePointFontIndirect](#createpointfontindirect), und verwenden Sie das Objekt Memberfunktionen zum Bearbeiten der Schriftartformats.  
  
 Die `CreatePointFont` und `CreatePointFontIndirect` Funktionen stellen oft leichter zu verwenden als `CreateFont` oder `CreateFontIndirect` , da sie die Konvertierung für die Höhe der Schriftart aus einem Punktgröße auf logische Einheiten automatisch lassen.  
  
 Weitere Informationen zu `CFont`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cfont"></a>CFont::CFont  
 Erstellt ein `CFont`-Objekt.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Hinweise  
 Das resultierende Objekt muss initialisiert werden, mit `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, oder `CreatePointFontIndirect` , bevor er verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>CFont::  
 Initialisiert ein `CFont` Objekt mit den angegebenen Merkmalen.  
  
```  
BOOL CreateFont(
    int nHeight,  
    int nWidth,  
    int nEscapement,  
    int nOrientation,  
    int nWeight,  
    BYTE bItalic,  
    BYTE bUnderline,  
    BYTE cStrikeOut,  
    BYTE nCharSet,  
    BYTE nOutPrecision,  
    BYTE nClipPrecision,  
    BYTE nQuality,  
    BYTE nPitchAndFamily,  
    LPCTSTR lpszFacename);
```  
  
### <a name="parameters"></a>Parameter  
 `nHeight`  
 Gibt die gewünschte Höhe (in logischen Einheiten) der Schriftart an. Finden Sie unter der `lfHeight` Mitglied der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)Struktur in das Windows SDK für eine Beschreibung. Der Absolute Wert des `nHeight` darf maximal 16.384 Geräteeinheiten aus, nachdem er konvertiert wird. Für alle Höhe Vergleiche sucht der Schriftartenmapper die größte Schriftart, die nicht die angeforderte Größe überschreitet oder die kleinste Schriftart alle Schriftarten die angeforderte Größe überschreiten.  
  
 `nWidth`  
 Gibt die durchschnittliche Breite (in logischen Einheiten) der Zeichen in der Schriftart an. Wenn `nWidth` gleich 0 ist, wird das Seitenverhältnis des Geräts das Seitenverhältnis Digitalisierung verfügbaren Schriftarten, die bestmögliche Übereinstimmung gefunden werden, die durch den absoluten Wert des Unterschieds bestimmt wird abgeglichen werden.  
  
 `nEscapement`  
 Gibt den Winkel (in Grad 0,1 Einheiten) zwischen der Vorschubvektor und die x-Achse des der Anzeigeoberfläche an. Der Vorschubvektor ist die Zeile über die Ursprünge an, der das erste und letzten Zeichen in einer Zeile. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse aus gemessen. Finden Sie unter der `lfEscapement` Element in der `LOGFONT` Struktur in das Windows SDK für Weitere Informationen.  
  
 `nOrientation`  
 Gibt den Winkel (in Grad 0,1 Einheiten) zwischen dem Basis-eines Zeichens und der x-Achse an. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse für Koordinatensysteme gemessen in der ist die y-Richtung nach unten und gegen den Uhrzeigersinn von der x-Achse für Koordinatensysteme, die in denen die y-Richtung nach oben weist.  
  
 `nWeight`  
 Gibt die Schriftbreite (in gezeichneten Pixel pro 1000) an. Finden Sie unter der `lfWeight` Element in der `LOGFONT` Struktur in das Windows SDK für Weitere Informationen. Die beschriebenen Werte sind ungefähre; die tatsächliche Darstellung hängt von der Schriftart ab. Einige Schriftarten haben nur `FW_NORMAL`, `FW_REGULAR`, und `FW_BOLD` Gewichtungen. Wenn `FW_DONTCARE` angegeben ist, wird eine standardgewichtung verwendet wird.  
  
 `bItalic`  
 Gibt an, ob die Schriftart kursiv formatiert ist.  
  
 `bUnderline`  
 Gibt an, ob die Schriftart unterstrichen ist.  
  
 `cStrikeOut`  
 Gibt an, ob die Zeichen in der Schriftart durchgestrichen sind. Gibt eine Schriftart durchgestrichen an, ob ein Wert ungleich NULL festgelegt.  
  
 `nCharSet`  
 Gibt die Schriftart Zeichen SetSee der `lfCharSet` Element in der `LOGFONT` Struktur in das Windows SDK für eine Liste von Werten.  
  
 Die OEM-Zeichensatz ist systemabhängig.  
  
 Schriftarten mit anderen Zeichensätzen können im System vorhanden. Eine Anwendung, die eine Schriftart mit einem unbekannten Zeichensatz verwendet, dürfen nicht versuchen, übersetzt oder zur Auswertung von Zeichenfolgen, die mit dieser Schriftart gerendert werden soll. Zeichenfolgen sollten stattdessen direkt an der Gerätetreiber für die Ausgabe übergeben werden.  
  
 Der Schriftartenmapper verwendet nicht die `DEFAULT_CHARSET` Wert. Eine Anwendung kann diesen Wert verwenden, um den Namen und die Größe einer Schriftart, um die logische Schriftart vollständig beschreiben zu ermöglichen. Wenn eine Schriftart mit dem angegebenen Namen nicht vorhanden ist, kann eine Schriftart aus jeder beliebige Zeichensatz für die angegebene Schriftart ersetzt werden. Um unerwartete Ergebnisse zu vermeiden, sollten Anwendungen verwenden die `DEFAULT_CHARSET` Wert nur selten.  
  
 `nOutPrecision`  
 Gibt die gewünschte Ausgabe Genauigkeit. Die Genauigkeit der Ausgabe definiert, wie genau die Ausgabe der angeforderten Schriftart Höhe, Breite Zeichen Ausrichtung, Vorschub und Tonhöhe übereinstimmen muss. Finden Sie unter der `lfOutPrecision` Element in der `LOGFONT` Struktur in das Windows SDK für eine Liste von Werten und Weitere Informationen.  
  
 `nClipPrecision`  
 Gibt die gewünschte Clipping Genauigkeit. Genauigkeit für das Ausschneiden definiert, wie Zeichen, die teilweise außerhalb des Clippingbereichs sind. Finden Sie unter der `lfClipPrecision` Element in der `LOGFONT` Struktur in das Windows SDK für eine Liste von Werten.  
  
 Eine Anwendung muss für die Verwendung eine eingebettete nur-Lese Schriftart angeben `CLIP_ENCAPSULATE`.  
  
 Um konsistent Drehung des Geräts, TrueType und Vektorschriftarten zu erreichen, kann eine Anwendung den OR-Operator verwenden, um Kombinieren der `CLIP_LH_ANGLES` Wert mit beliebigen anderen `nClipPrecision` Werte. Wenn die `CLIP_LH_ANGLES` Bit festgelegt ist, wird die Rotation für alle Schriftarten, hängt davon ab, ob die Ausrichtung des Koordinatensystems Linkshändig ist oder rechtshändige. (Weitere Informationen zu die Ausrichtung des Koordinatensysteme, finden Sie unter der Beschreibung der `nOrientation` Parameter.) Wenn `CLIP_LH_ANGLES` ist nicht festgelegt, Schriftarten immer gegen den Uhrzeigersinn, aber die Rotation eines anderen Schriftarten ist abhängig von der Ausrichtung des Koordinatensystems.  
  
 `nQuality`  
 Gibt die Ausgabequalitäten die Schriftart, die definiert, wie sorgfältig die GDI versuchen muss, die logische Schriftart-Attribute, die denen des eigentlichen physischen Schriftart entsprechend an. Finden Sie unter der `lfQuality` Element in der `LOGFONT` Struktur in das Windows SDK für eine Liste von Werten.  
  
 `nPitchAndFamily`  
 Gibt die Schriftbreite und Familie der Schriftart an. Finden Sie unter der `lfPitchAndFamily` Element in der `LOGFONT` Struktur in das Windows SDK für eine Liste von Werten und Weitere Informationen.  
  
 `lpszFacename`  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf maximal 30 Zeichen lang sein. Die Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) Funktion kann verwendet werden, um alle derzeit verfügbaren Schriftarten aufzulisten. Wenn `lpszFacename` ist `NULL`, GDI verwendet eine geräteunabhängige Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann später als die Schriftart für alle Gerätekontext ausgewählt werden.  
  
 Die `CreateFont` Funktion erstellt eine neue Windows-GDI-Schriftart nicht. Er wählt lediglich die bestmögliche Übereinstimmung aus den verfügbaren physischen Schriftarten auf die GDI.  
  
 Anwendungen können die Standardeinstellungen für die meisten Parameter verwenden, für die Erstellung eine logischen Schriftart. Die Parameter, die immer bestimmte Werte zugewiesen werden soll, sind `nHeight` und `lpszFacename`. Wenn `nHeight` und `lpszFacename` nicht festgelegt werden von der Anwendung ist die logische Schriftart, die erstellt wird vom Gerät abhängig.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt, indem die `CreateFont` funktionieren, verwenden Sie `CDC::SelectObject` um eine andere Schriftart in den Gerätekontext ausgewählt haben, löschen Sie Sie dann die `CFont` -Objekt, das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>CFont::CreateFontIndirect  
 Initialisiert eine `CFont` mit den Merkmalen, die im angegebenen Objekt ein [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)Struktur.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogFont`  
 Verweist auf eine `LOGFONT` -Struktur, die die Eigenschaften der die logische Schriftart definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann später als die aktuelle Schriftart für jedes Gerät ausgewählt werden.  
  
 Diese Schriftart hat die Eigenschaften, die im angegebenen der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur. Wenn die Schriftart aktiviert ist, mithilfe der [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) Memberfunktion, die GDI-Schriftart-Mapper versucht, die logische Schriftart mit einem vorhandenen physischen Schriftart entsprechend. Fällt der Schriftartenmapper für die logische Schriftart keine genaue Übereinstimmung gefunden, wird eine alternative Schriftart, so viele wie möglich die angeforderten Eigenschaften, deren Merkmalen übereinstimmen.  
  
 Wenn Sie nicht mehr benötigen die `CFont` Objekt erstellt, indem die `CreateFontIndirect` funktionieren, verwenden Sie `CDC::SelectObject` um eine andere Schriftart in den Gerätekontext ausgewählt haben, löschen Sie Sie dann die `CFont` -Objekt, das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>CFont::CreatePointFont  
 Diese Funktion bietet eine einfache Möglichkeit zum Erstellen einer Schriftart für eine angegebene Schriftart und Schriftgrad.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nPointSize`  
 Die Höhe der Schriftart in Zehntelsekunden eines Punkts wird angefordert. (Z. B. übergeben Sie 120 zum Anfordern einer Schriftart 12 Punkt.)  
  
 `lpszFaceName`  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf maximal 30 Zeichen lang sein. Die Windows **EnumFontFamilies** Funktion kann verwendet werden, um alle derzeit verfügbaren Schriftarten aufzulisten. Wenn `lpszFaceName` ist **NULL**, GDI verwendet eine geräteunabhängige Schriftart.  
  
 `pDC`  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das verwendet werden, konvertieren die Höhe in `nPointSize` zu logischen Einheiten. Wenn **NULL**, ein Bildschirm Gerätekontext für die Konvertierung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe in automatisch konvertiert `nPointSize` auf logischen Einheiten, die mithilfe der `CDC` Objekt verweist `pDC`.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt wird, die `CreatePointFont` funktionieren, zunächst wählen Sie die Schriftart im Gerätekontext, löschen Sie die `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect  
 Diese Funktion ist identisch mit [CreateFontIndirect](#createfontindirect) mit dem Unterschied, dass die **LfHeight** Mitglied der `LOGFONT` in Zehntelsekunden ein Punkt anstatt Gerät Einheiten interpretiert wird.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogFont`  
 Verweist auf eine [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) -Struktur, die die Eigenschaften der die logische Schriftart definiert. Die **LfHeight** Mitglied der `LOGFONT` Struktur in Zehntelsekunden ein Punkt anstatt auf logischen Einheiten gemessen wird. (Legen Sie z. B. **LfHeight** 120 eine Schriftart 12 Punkt anfordern.)  
  
 `pDC`  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das verwendet werden, konvertieren die Höhe in **LfHeight** zu logischen Einheiten. Wenn **NULL**, ein Bildschirm Gerätekontext für die Konvertierung verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion konvertiert automatisch die Höhe in **LfHeight** auf logischen Einheiten, die mithilfe der `CDC` Objekt verweist `pDC` vor der Übergabe der `LOGFONT` Struktur sich bei Windows.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt wird, die `CreatePointFontIndirect` funktionieren, zunächst wählen Sie die Schriftart im Gerätekontext, löschen Sie die `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CFont::FromHandle  
 Gibt einen Zeiger auf eine `CFont` Objekt, wenn ein **HFONT** handle für ein Windows-GDI-Schriftart-Objekt.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>Parameter  
 `hFont`  
 Ein **HFONT** handle für eine Windows-Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CFont` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CFont` Objekt ist nicht bereits angefügt an das Handle, das einen temporären `CFont` Objekt erstellt und angefügt. Dieser temporäre `CFont` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu dem alle temporären Grafik Zeit Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass nur während der Verarbeitung der Nachricht von einem Fenster das temporäre Objekt gültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>CFont::GetLogFont  
 Mit dieser Funktion wird zum Abrufen einer Kopie der `LOGFONT` -Struktur für `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogFont*  
 Zeiger auf die [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur der Schriftartinformationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>CFont::operator HFONT  
 Verwenden Sie diesen Operator zum Abrufen der Windows-GDI-Handle der Schriftart an, an der die `CFont` Objekt.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Windows-GDI-Schriftart-Objekt angefügt, um `CFont` Wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Da dieser Operator automatisch für Konvertierungen von verwendet wird `CFont` auf [Schriftarten und Text](http://msdn.microsoft.com/library/windows/desktop/dd144819), können Sie übergeben `CFont` Objekte an Funktionen, die voraussichtlich **HFONT**s.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




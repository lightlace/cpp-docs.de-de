---
title: CFont-Klasse | Microsoft-Dokumentation
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
- CFont class
- GDI, font classes
- fonts, MFC classes
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cc7ecfb850bf24013acdb55075eeb3d64d4994ee
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cfont-class"></a>CFont-Klasse
Kapselt eine Schriftart der Windows GDI (Graphics Device Interface) und stellt Memberfunktionen zum Bearbeiten der Schriftart bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|Erstellt ein `CFont`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::](#createfont)|Initialisiert eine `CFont` mit den angegebenen Merkmalen.|  
|[CFont::CreateFontIndirect](#createfontindirect)|Initialisiert eine `CFont` mit den Eigenschaften, die im angegebenen Objekt ein `LOGFONT` Struktur.|  
|[CFont::CreatePointFont](#createpointfont)|Initialisiert eine `CFont` mit der angegebenen Höhe gemessen, Uhrzeitdaten ein Punkt, und klicken Sie auf Schriftart.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Identisch mit `CreateFontIndirect` mit der Ausnahme, dass die Höhe der Schriftart in Zehntelsekunden ein Punkt anstatt von logischen Einheiten gemessen wird.|  
|[CFont::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CFont` bei einer Windows-Objekt **HFONT**.|  
|[CFont::GetLogFont](#getlogfont)|Füllt ein `LOGFONT` mit Informationen über die logische Schriftart, an der die `CFont` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|Gibt das Windows-GDI-Schriftart-Handle an die `CFont` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CFont` Objekt, das Erstellen einer `CFont` Objekt, und fügen Sie eine Windows-Schriftart mit [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), oder [CreatePointFontIndirect](#createpointfontindirect), und dann Memberfunktionen des Objekts verwenden, um die Schriftart zu ändern.  
  
 Die `CreatePointFont` und `CreatePointFontIndirect` Funktionen sind häufig einfacher zu verwenden als `CreateFont` oder `CreateFontIndirect` , da die Konvertierung für die Höhe der Schriftart von einer Punktgröße auf logische Einheiten automatisch dazu.  
  
 Weitere Informationen zu `CFont`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
 Das resultierende Objekt muss initialisiert werden, mit `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, oder `CreatePointFontIndirect` , bevor sie verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#70;](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>CFont::  
 Initialisiert ein `CFont` -Objekt mit den angegebenen Eigenschaften.  
  
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
 Gibt die gewünschte Höhe (in logischen Einheiten) der Schriftart an. Finden Sie unter der `lfHeight` Mitglied der ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037)-Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beschreibung. Der Absolute Wert des `nHeight` 16.384 Geräteeinheiten nach der Konvertierung nicht überschreiten. Für alle Höhe Vergleiche sucht Font Mapper die größte Schriftart, die nicht die angeforderte Größe überschreitet oder die kleinste Schriftart alle Schriftarten auf die angeforderte Größe überschreiten.  
  
 `nWidth`  
 Gibt die durchschnittliche Breite (in logischen Einheiten) der Zeichen in der Schriftart an. Wenn `nWidth` gleich 0 ist, wird das Seitenverhältnis des Geräts das Seitenverhältnis Digitalisierung von den verfügbaren Schriftarten am ehesten entspricht, die durch den absoluten Wert des Unterschieds bestimmt wird abgeglichen werden.  
  
 `nEscapement`  
 Gibt den Winkel (in Einheiten von 0,1 Grad) zwischen der Vorschubvektor und der x-Achse der Anzeigeoberfläche. Der Vektor "Escapement" ist die Zeile über die Ursprünge der ersten und letzten Zeichen in einer Zeile. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse aus gemessen. Finden Sie unter der `lfEscapement` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen.  
  
 `nOrientation`  
 Gibt den Winkel (in Grad 0,1 Einheiten) zwischen den geplanten eines Zeichens und die x-Achse. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse für Koordinatensysteme gemessen in der die y-Richtung ist unten, und der Ausrichtungslinie für Koordinatensysteme, in denen die y-Richtung aktiv ist.  
  
 `nWeight`  
 Gibt die Schriftbreite (in gezeichneten Pixel pro 1000). Finden Sie unter der `lfWeight` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen. Die beschriebenen Werte sind ungefähre. die tatsächliche Darstellung hängt von der Schriftart ab. Manche Schriftarten haben nur `FW_NORMAL`, `FW_REGULAR`, und `FW_BOLD` stärken. Wenn `FW_DONTCARE` angegeben ist, wird eine standardgewichtung verwendet wird.  
  
 `bItalic`  
 Gibt an, ob die Schriftart kursiv ist.  
  
 `bUnderline`  
 Gibt an, ob die Schrift unterstrichen ist.  
  
 `cStrikeOut`  
 Gibt an, ob die Zeichen in der Schriftart durchgestrichen sind. Gibt eine Schriftart durchgestrichen an, ob ein Wert ungleich NULL festgelegt.  
  
 `nCharSet`  
 Gibt die Schriftart Zeichen SetSee der `lfCharSet` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
 Die OEM-Zeichensatz hängt vom jeweiligen System ab.  
  
 Schriftarten mit anderen Zeichensätzen möglicherweise im System vorhanden. Eine Anwendung, die eine Schriftart mit einem unbekannten Zeichensatz verwendet, dürfen nicht versuchen, übersetzen oder zur Auswertung von Zeichenfolgen, die mit dieser Schriftart gerendert werden soll. Stattdessen sollte die Zeichenfolgen direkt an die Ausgabe des Gerätetreibers übergeben werden.  
  
 Font Mapper verwendet nicht die `DEFAULT_CHARSET` Wert. Eine Anwendung kann diesen Wert verwenden, um den Namen und die Größe einer Schriftart die logische Schriftart vollständig beschreiben zu ermöglichen. Wenn eine Schriftart mit dem angegebenen Namen nicht vorhanden ist, kann eine Schriftart aus einem Zeichensatz für die angegebene Schriftart ersetzt werden. Um unerwartete Ergebnisse zu vermeiden, sollten Clientanwendungen verwenden die `DEFAULT_CHARSET` sparsam Wert.  
  
 `nOutPrecision`  
 Gibt die Genauigkeit der gewünschten Ausgabe. Die Genauigkeit der Ausgabe definiert, wie genau die Ausgabe der angeforderten Schriftart Höhe, Breite, Ausrichtung Zeichen, "Escapement" und Tonhöhe übereinstimmen muss. Finden Sie unter der `lfOutPrecision` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der Werte und Weitere Informationen.  
  
 `nClipPrecision`  
 Gibt die gewünschte Clipping Genauigkeit. Genauigkeit für das Ausschneiden definiert, wie Zeichen, die teilweise außerhalb des Ausschneidebereichs. Finden Sie unter der `lfClipPrecision` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
 Um nur-Lese Schriftart zu verwenden, eine Anwendung angeben muss `CLIP_ENCAPSULATE`.  
  
 Um konsistent Drehung und TrueType und Vektorschriftarten zu erreichen, eine Anwendung kann mithilfe den OR-Operator Kombinieren der `CLIP_LH_ANGLES` Wert mit allen anderen `nClipPrecision` Werte. Wenn die `CLIP_LH_ANGLES` Bit festgelegt ist, die Drehung für alle Schriftarten, hängt davon ab, ob die Orientierung des Koordinatensystems Linkshänder ist oder. (Weitere Informationen über die Ausrichtung von Koordinatensystemen finden Sie unter der Beschreibung der `nOrientation` Parameter.) Wenn `CLIP_LH_ANGLES` ist nicht festgelegt, Geräteschriftarten immer gegen den Uhrzeigersinn, aber die Drehung der anderen Schriftarten ist abhängig von der Ausrichtung des Koordinatensystems.  
  
 `nQuality`  
 Gibt die Ausgabequalitäten die Schriftart, die definiert, wie sorgfältig die GDI versuchen muss, die logische Schriftart-Attribute, mit denen der eigentlichen physikalischen Schriftart anpassen. Finden Sie unter der `lfQuality` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste von Werten.  
  
 `nPitchAndFamily`  
 Gibt die Zeichenbreite und Familie der Schriftart an. Finden Sie unter der `lfPitchAndFamily` Element in der `LOGFONT` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der Werte und Weitere Informationen.  
  
 `lpszFacename`  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf maximal 30 Zeichen lang sein. Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) -Funktion kann verwendet werden, um alle derzeit verfügbaren Schriftarten aufzulisten. Wenn `lpszFacename` ist `NULL`, die GDI verwendet eine geräteunabhängige Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann anschließend als Schriftart für alle Gerätekontext ausgewählt werden.  
  
 Die `CreateFont` Funktion erstellt eine neue Windows-GDI-Schriftart nicht. Es wählt lediglich am ehesten entspricht aus verfügbaren physischen Schriftarten in die GDI.  
  
 Clientanwendungen können die Standardeinstellungen für die meisten Parameter, wenn eine logische Schriftart erstellen. Der Parameter, der immer bestimmte Werte zugewiesen werden soll, sind `nHeight` und `lpszFacename`. Wenn `nHeight` und `lpszFacename` nicht festgelegt ist vom Gerät abhängig von der Anwendung die logische Schriftart, die erstellt wird.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt, indem der `CreateFont` funktioniert, verwenden Sie `CDC::SelectObject` löschen Sie eine andere Schriftart im Gerätekontext aus, die `CFont` , das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#71;](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>CFont::CreateFontIndirect  
 Initialisiert eine `CFont` mit den Eigenschaften, die im angegebenen Objekt ein [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)Struktur.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogFont`  
 Verweist auf eine `LOGFONT` -Struktur, die die Merkmale der logische Schriftart definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann später als die aktuelle Schriftart für jedes Gerät ausgewählt werden.  
  
 Diese Schriftart weist die Merkmale, die gemäß der [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur. Bei Auswahl die Schriftart mithilfe der [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) -Memberfunktion, die GDI Font Mapper versucht, die logische Schriftart einer vorhandenen physikalischen Schriftart. Wenn Font Mapper eine genaue Übereinstimmung für die logische Schriftart gefunden, wird eine alternative Schriftart, deren Eigenschaften so viele der angeforderten Eigenschaften wie möglich übereinstimmen.  
  
 Wenn Sie nicht mehr benötigen die `CFont` Objekt erstellt, indem der `CreateFontIndirect` funktioniert, verwenden Sie `CDC::SelectObject` löschen Sie eine andere Schriftart im Gerätekontext aus, der `CFont` , das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#72;](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
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
 Die angeforderte Höhe der Schriftart Uhrzeitdaten eines Punkts. (Z. B. übergeben Sie 120 zum Anfordern einer Schriftart 12 Punkt.)  
  
 `lpszFaceName`  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf maximal 30 Zeichen lang sein. Windows **EnumFontFamilies** -Funktion kann verwendet werden, um alle derzeit verfügbaren Schriftarten aufzulisten. Wenn `lpszFaceName` ist **NULL**, die GDI verwendet eine geräteunabhängige Schriftart.  
  
 `pDC`  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) -Objekt, das verwendet werden, konvertieren die Höhe in `nPointSize` auf logische Einheiten. Wenn **NULL**, ein Bildschirm-Gerätekontext wird für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe in automatisch konvertiert `nPointSize` auf logische Einheiten, die mit der `CDC` Objekt verweist `pDC`.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt, indem die `CreatePointFont` funktioniert, wählen Sie die Schriftart aus den Gerätekontext zunächst Löschen der `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#73;](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect  
 Diese Funktion ist identisch mit [CreateFontIndirect](#createfontindirect) mit dem Unterschied, dass die **LfHeight** Mitglied der `LOGFONT` wird ein Punkt anstatt Gerät Einheiten Uhrzeitdaten interpretiert.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogFont`  
 Verweist auf eine ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037) -Struktur, die die Merkmale der logische Schriftart definiert. Die **LfHeight** Mitglied der `LOGFONT` Struktur in Zehntelsekunden ein Punkt anstatt von logischen Einheiten gemessen wird. (Legen Sie z. B. **LfHeight** 120 eine Schriftart 12 Punkt anfordern.)  
  
 `pDC`  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) -Objekt, das verwendet werden, konvertieren die Höhe in **LfHeight** auf logische Einheiten. Wenn **NULL**, ein Bildschirm-Gerätekontext wird für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion konvertiert automatisch die Höhe in **LfHeight** auf logische Einheiten, die mit der `CDC` Objekt verweist `pDC` vor der Übergabe der `LOGFONT` Struktur an Windows.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt, indem die `CreatePointFontIndirect` funktioniert, wählen Sie die Schriftart aus den Gerätekontext zunächst Löschen der `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#74;](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CFont::FromHandle  
 Gibt einen Zeiger auf eine `CFont` Objekt, wenn bei einer **HFONT** handle für ein Windows-GDI-Schriftart-Objekt.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>Parameter  
 `hFont`  
 Ein **HFONT** handle für eine Windows-Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CFont` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CFont` Objekt noch nicht angefügt an das Handle, ein temporäres `CFont` Objekt erstellt und angefügt wird. Dieser temporäre `CFont` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife aufweist, zu der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#75;](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>CFont::GetLogFont  
 Rufen Sie diese Funktion zum Abrufen einer Kopie von der `LOGFONT` Struktur für `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogFont*  
 Zeiger auf die [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur zum Empfangen von Informationen über den.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#76;](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>CFont::operator HFONT  
 Verwenden Sie diesen Operator zum Abrufen der Windows GDI-Handle für die Schriftart, die an der der `CFont` Objekt.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Windows-GDI-Schriftart-Objekt an der `CFont` Wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Da dieser Operator automatisch für die Konvertierung von verwendet wird `CFont` auf [Schriftarten und Text](http://msdn.microsoft.com/library/windows/desktop/dd144819), können Sie übergeben `CFont` Objekte, Funktionen, die erwarten, dass **HFONT**s.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie unter [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#77;](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)





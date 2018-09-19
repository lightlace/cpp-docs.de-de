---
title: CFont-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2781a41ddadc6932e1c5797f098407b7dd5e4f29
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221227"
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
|[CFont::CreateFontIndirect](#createfontindirect)|Initialisiert eine `CFont` Objekt mit den Eigenschaften, die im angegebenen ein `LOGFONT` Struktur.|  
|[CFont::CreatePointFont](#createpointfont)|Initialisiert eine `CFont` mit der angegebenen Höhe, gemessen in Zehnteln einer zeigen, und die Schriftart.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|Identisch mit `CreateFontIndirect` mit dem Unterschied, dass die Höhe der Schriftart in Zehntelsekunden ein Punkt anstelle von logischen Einheiten gemessen wird.|  
|[CFont::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CFont` Objekt, wenn ein Windows-HFONT angegeben.|  
|[CFont::GetLogFont](#getlogfont)|Füllt ein `LOGFONT` mit Informationen über die logische Schriftart, die angefügt werden, um die `CFont` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFont::operator HFONT](#operator_hfont)|Gibt das Windows-GDI-Schriftart-Handle an die `CFont` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden einer `CFont` Objekt, das Erstellen einer `CFont` Objekt aus, und fügen Sie eine Windows-Schriftart mit [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), oder [CreatePointFontIndirect](#createpointfontindirect), und klicken Sie dann Memberfunktionen des Objekts verwenden, um die Schriftart zu bearbeiten.  
  
 Die `CreatePointFont` und `CreatePointFontIndirect` Funktionen sind häufig einfacher zu verwenden als `CreateFont` oder `CreateFontIndirect` da sie die Konvertierung für die Höhe der Schriftart von einer Punktgröße auf logische Einheiten automatisch übernehmen.  
  
 Weitere Informationen zu `CFont`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cfont"></a>  CFont::CFont  
 Erstellt ein `CFont`-Objekt.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>Hinweise  
 Das resultierende Objekt muss initialisiert werden, mit `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, oder `CreatePointFontIndirect` , bevor sie verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#70](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="createfont"></a>  CFont::  
 Initialisiert eine `CFont` Objekt mit den angegebenen Merkmalen.  
  
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
 *nHeight*  
 Gibt die gewünschte Höhe (in logischen Einheiten) der Schriftart an. Finden Sie unter den `lfHeight` Mitglied der ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)Struktur im Windows SDK für eine Beschreibung. Der Absolute Wert des *nHeight* darf 16.384 Geräteeinheiten nicht überschreiten, nach der Konvertierung ist. Für alle Höhe Vergleiche sucht der Schriftartenmapper die größte Schriftart, die nicht die angeforderte Größe überschreitet oder die kleinste Schriftart alle Schriftarten auf die angeforderte Größe überschreiten.  
  
 *nWidth*  
 Gibt die durchschnittliche Breite (in logischen Einheiten) der Zeichen in der Schriftart an. Wenn *nWidth* gleich 0 ist, wird das Seitenverhältnis des Geräts die Digitalisierung Seitenverhältnis von Schriftarten auf die bestmögliche Übereinstimmung wurde gefunden, das durch den absoluten Wert des Unterschieds bestimmt wird abgeglichen werden.  
  
 *nEscapement*  
 Gibt den Winkel (in Einheiten von 0,1 Grad) zwischen dem Vorschubvektor und der x-Achse der Anzeigeoberfläche. Der Vektor "Escapement" ist die Zeile über die Ursprünge der ersten und letzten Zeichen in einer Zeile. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse aus gemessen. Finden Sie unter den `lfEscapement` Element in der `LOGFONT` Struktur im Windows SDK für Weitere Informationen.  
  
 *nOrientation*  
 Gibt den Winkel (in Einheiten von 0,1 Grad) zwischen der Baseline der ein Zeichen und der x-Achse. Der Winkel wird gegen den Uhrzeigersinn von der x-Achse für Koordinatensysteme gemessen in dem ist die y-Richtung nach unten, und im Uhrzeigersinn von der x-Achse für Koordinatensysteme, die in denen y-Richtung aktiv ist.  
  
 *nWeight*  
 Gibt die Schriftbreite (in gezeichneten Pixel pro 1000). Finden Sie unter den *LfWeight* Element in der `LOGFONT` Struktur im Windows SDK für Weitere Informationen. Die beschriebenen Werte sind ungefähre Werte; die tatsächliche Darstellung hängt von der Schriftart ab. Einige Schriftarten haben nur FW_NORMAL FW_REGULAR und FW_BOLD Gewichtungen. Wenn FW_DONTCARE angegeben wird, wird eine standardgewichtung verwendet.  
  
 *bItalic*  
 Gibt an, ob die Schriftart kursiv formatiert ist.  
  
 *bUnderline*  
 Gibt an, ob die Schriftart unterstrichen formatiert ist.  
  
 *cStrikeOut*  
 Gibt an, ob die Zeichen in die Schriftart durchgestrichen sind. Gibt eine durchgestrichene Schriftart an, ob auf einen Wert ungleich NULL festgelegt.  
  
 *nCharSet*  
 Gibt an, die Schriftart Zeichen SetSee der `lfCharSet` Element in der `LOGFONT` Struktur im Windows SDK für eine Liste von Werten.  
  
 Die OEM-Zeichensatz ist systemabhängig.  
  
 Schriftarten mit anderen Zeichensätzen ist möglicherweise im System vorhanden. Eine Anwendung, die eine Schriftart mit einem Zeichensatz Unbekannter dürfen nicht versuchen, übersetzen oder zur Auswertung von Zeichenfolgen, die in dieser Schriftart gerendert werden soll. Stattdessen sollte die Zeichenfolgen direkt an der Gerätetreiber für die Ausgabe übergeben werden.  
  
 Der Schriftartenmapper wird die DEFAULT_CHARSET-Wert nicht verwendet werden. Eine Anwendung kann diesen Wert verwenden, um den Namen und die Größe einer Schriftart detailliert beschreiben, die logische Schriftart zu ermöglichen. Wenn eine Schriftart mit dem angegebenen Namen nicht vorhanden ist, kann eine Schriftart aus beliebiger Zeichensatz für die angegebene Schriftart ersetzt werden. Um unerwartete Ergebnisse zu vermeiden, sollten Anwendungen die DEFAULT_CHARSET Wert nur selten verwenden.  
  
 *nOutPrecision*  
 Gibt an, die Genauigkeit der gewünschten Ausgabe. Die Genauigkeit der Ausgabe definiert, wie genau die Ausgabe der angeforderten Schriftart Höhe, Breite, Ausrichtung Zeichen, "Escapement" und Pitch übereinstimmen muss. Finden Sie unter den `lfOutPrecision` Element in der `LOGFONT` Struktur im Windows SDK für eine Liste von Werten und Weitere Informationen.  
  
 *nClipPrecision*  
 Gibt die gewünschte Clipping Genauigkeit. Genauigkeit für das Ausschneiden definiert, wie Zeichen, die sich teilweise außerhalb des Clippingbereichs befinden. Finden Sie unter den `lfClipPrecision` Element in der `LOGFONT` Struktur im Windows SDK für eine Liste von Werten.  
  
 Um einen eingebetteten nur-Lese Schriftart verwendet wird, muss eine Anwendung CLIP_ENCAPSULATE angeben.  
  
 Um konsistent Drehung des Geräts und TrueType-Vektorschriftarten zu erreichen, kann eine Anwendung den OR-Operator verwenden, die CLIP_LH_ANGLES Wert kombinieren, um mit beliebigen anderen *nClipPrecision* Werte. Wenn das CLIP_LH_ANGLES Bit festgelegt ist, die Drehung für alle Schriftarten abhängig, ob die Ausrichtung des Koordinatensystems für Linkshänder ist oder. (Weitere Informationen zu die Ausrichtung des Koordinatensysteme, finden Sie unter der Beschreibung der *nOrientation* Parameter.) Wenn CLIP_LH_ANGLES nicht festgelegt ist, Geräteschriftarten wird immer gegen den Uhrzeigersinn drehen, aber die Drehung der anderen Schriftarten ist abhängig von der Ausrichtung des Koordinatensystems.  
  
 *nQuality*  
 Gibt die Ausgabequalitäten der Schriftart, die definiert, wie sorgfältig GDI versuchen muss, die logische Schriftart-Attribute, mit denen der tatsächlichen physikalischen Schriftart entsprechend an. Finden Sie unter den `lfQuality` Element in der `LOGFONT` Struktur im Windows SDK für eine Liste von Werten.  
  
 *nPitchAndFamily*  
 Gibt Dichte und Familie der Schriftart an. Finden Sie unter den `lfPitchAndFamily` Element in der `LOGFONT` Struktur im Windows SDK für eine Liste von Werten und Weitere Informationen.  
  
 *lpszFacename*  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf 30 Zeichen nicht überschreiten. Die Windows [EnumFontFamilies](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesa) Funktion kann zum Aufzählen aller derzeit verfügbaren Schriftarten verwendet werden. Wenn *LpszFacename* NULL ist, die GDI verwendet eine geräteunabhängige Schriftart ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann anschließend als Schriftart für einen beliebigen Gerätekontext ausgewählt werden.  
  
 Die `CreateFont` Funktion erstellt eine neue Windows-GDI-Schriftart nicht. Er wählt lediglich die bestmögliche Übereinstimmung aus den verfügbaren physischen Schriftarten zu GDI.  
  
 Anwendungen können die Standardeinstellungen für die meisten Parameter verwenden, wenn Sie eine logische Schriftart erstellen. Der Parameter, die immer bestimmte Werte zugewiesen werden soll, sind *nHeight* und *LpszFacename*. Wenn *nHeight* und *LpszFacename* nicht festgelegt werden von der Anwendung ist die logische Schriftart, die erstellt wird vom Gerät abhängig.  
  
 Wenn Sie fertig sind, mit der `CFont` Objekt erstellt wurde, indem die `CreateFont` funktionieren, verwenden Sie `CDC::SelectObject` löschen Sie eine andere Schriftart für den Gerätekontext aus, klicken Sie dann die `CFont` -Objekt, das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#71](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="createfontindirect"></a>  CFont::CreateFontIndirect  
 Initialisiert eine `CFont` Objekt mit den Eigenschaften, die im angegebenen ein ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)Struktur.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 *lpLogFont*  
 Verweist auf eine `LOGFONT` Struktur, die die Merkmale der logische Schriftart definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Schriftart kann anschließend als die aktuelle Schriftart für beliebige Geräte ausgewählt werden.  
  
 Diese Schriftart verfügt über die Eigenschaften, die im angegebenen die ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur. Wenn die Schriftart ausgewählt ist, mithilfe der [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) Memberfunktion wird die GDI-Schriftart-Mapper versucht, logische Schriftart mit einer vorhandenen physischen Schriftart entsprechend. Wenn der Schriftartenmapper eine genaue Übereinstimmung für die logische Schriftart zu finden, wird eine alternative Schriftart, deren Eigenschaften so viele der angeforderten Eigenschaften wie möglich übereinstimmen.  
  
 Wenn Sie nicht mehr benötigen die `CFont` Objekt erstellt wurde, indem die `CreateFontIndirect` funktionieren, verwenden Sie `CDC::SelectObject` löschen Sie eine andere Schriftart für den Gerätekontext aus, klicken Sie dann die `CFont` -Objekt, das nicht mehr benötigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#72](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="createpointfont"></a>  CFont::CreatePointFont  
 Diese Funktion bietet eine einfache Möglichkeit zum Erstellen einer Schriftart von einer angegebenen Schriftart und Schriftgrad.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nPointSize*  
 Angeforderte Höhe der Schriftart in Zehnteln eines Punkts. (Z. B. übergeben Sie 120 zum Anfordern einer Schriftart 12 Punkt.)  
  
 *lpszFaceName*  
 Ein `CString` oder ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Schriftart angibt. Die Länge dieser Zeichenfolge darf 30 Zeichen nicht überschreiten. Die Windows ' EnumFontFamilies-Funktion kann zum Aufzählen aller derzeit verfügbaren Schriftarten verwendet werden. Wenn *LpszFaceName* NULL ist, die GDI verwendet eine geräteunabhängige Schriftart ab.  
  
 *pDC*  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das verwendet werden, konvertieren die Höhe in *nPointSize* auf logischen Einheiten. Wenn NULL ist, wird ein Bildschirm Gerätekontext für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Konvertiert sie automatisch die Höhe in *nPointSize* auf logische Einheiten unter Verwendung des CDC-Objekts verweist *pDC*.  
  
 Wenn Sie fertig sind, mit der `CFont` von erstelltes Objekt die `CreatePointFont` funktionieren müssen zunächst die Schriftart im Gerätekontext auswählen und dann löschen Sie die `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#73](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="createpointfontindirect"></a>  CFont::CreatePointFontIndirect  
 Diese Funktion ist identisch mit [CreateFontIndirect](#createfontindirect) mit dem Unterschied, dass die `lfHeight` Mitglied der `LOGFONT` wird in Zehntelsekunden ein Punkt anstatt Gerät Einheiten interpretiert.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpLogFont*  
 Verweist auf eine ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur, die die Merkmale der logische Schriftart definiert. Die `lfHeight` Mitglied der `LOGFONT` Struktur wird in Zehntelsekunden ein Punkt anstelle von logischen Einheiten gemessen. (Legen Sie z. B. `lfHeight` 120 eine Schriftart 12 Punkt anfordern.)  
  
 *pDC*  
 Zeiger auf die [CDC](../../mfc/reference/cdc-class.md) Objekt, das verwendet werden, konvertieren die Höhe in `lfHeight` auf logischen Einheiten. Wenn NULL ist, wird ein Bildschirm Gerätekontext für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion konvertiert automatisch die Höhe in `lfHeight` auf logische Einheiten unter Verwendung des CDC-Objekts verweist *pDC* vor der Übergabe der `LOGFONT` Struktur an Windows.  
  
 Wenn Sie fertig sind, mit der `CFont` von erstelltes Objekt die `CreatePointFontIndirect` funktionieren müssen zunächst die Schriftart im Gerätekontext auswählen und dann löschen Sie die `CFont` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#74](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CFont::FromHandle  
 Gibt einen Zeiger auf eine `CFont` Objekt, wenn einen HFONT-Handle an ein Windows-GDI-Schriftart-Objekt übergeben.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>Parameter  
 *hFont*  
 Ein HFONT-Handle für eine Windows-Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CFont` -Objekt, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CFont` Objekt ist noch nicht auf das Handle, eine temporäre angefügt `CFont` Objekt erstellt und angefügt. Diese temporären `CFont` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, an der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass das temporäre Objekt nur während der Verarbeitung der Nachricht für ein Fenster gültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#75](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="getlogfont"></a>  CFont::GetLogFont  
 Mit dieser Funktion wird zum Abrufen einer Kopie der `LOGFONT` -Struktur für `CFont`.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>Parameter  
 *pLogFont*  
 Zeiger auf die ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) Struktur zum Empfangen von Informationen über den.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Funktion erfolgreich ist, andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#76](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="operator_hfont"></a>  CFont::operator HFONT  
 Verwenden Sie diesen Operator das Windows-GDI-Handle der Schriftart an angefügt Abrufen der `CFont` Objekt.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Objekts der Windows-GDI-Schriftart angefügt `CFont` Wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Da dieser Operator automatisch für Konvertierungen von verwendet wird `CFont` zu [Schriftarten und Text](/windows/desktop/gdi/fonts-and-text), können Sie übergeben `CFont` Objekte an Funktionen, die HFONTs erwarten.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten finden Sie unter [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#77](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




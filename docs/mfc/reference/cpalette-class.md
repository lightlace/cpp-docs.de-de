---
title: CPalette-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette class
- HPALETTE
- color palettes, MFC
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
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
ms.openlocfilehash: 6ccd389eaf765993c59311cc1041893f2cf9fbfa
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cpalette-class"></a>CPalette-Klasse
Kapselt eine Windows-Farbpalette.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|Erstellt ein `CPalette` -Objekt mit keine angefügten Palette von Windows. Initialisieren Sie die `CPalette` -Objekt mit einer der Initialisierung-Memberfunktionen, bevor es verwendet werden kann.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[: CPalette:: AnimatePalette](#animatepalette)|Einträge in der logischen Palette identifizierten ersetzt die `CPalette` Objekt. Die Anwendung verfügt nicht seines Clientbereichs aktualisieren, da Windows sofort die neuen Einträge in der Systempalette zugeordnet.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Erstellt eine Halbtonpalette für den Gerätekontext und fügt es der `CPalette` Objekt.|  
|[CPalette::CreatePalette](#createpalette)|Erstellt eine Windows-Farbpalette und fügt es der `CPalette` Objekt.|  
|[CPalette::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CPalette` Objekt, wenn ein Handle zu einer Windows-Palette-Objekt zu erhalten.|  
|[CPalette::GetEntryCount](#getentrycount)|Ruft die Anzahl der Paletteneinträge in einer logischen Palette ab.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Gibt den Index des Eintrags in der logischen Palette, die einen Farbwert am ehesten entspricht.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Ruft einen Bereich der Paletteneinträge in einer logischen Palette ab.|  
|[CPalette::ResizePalette](#resizepalette)|Ändert die Größe der angegebenen logischen Palette der `CPalette` Objekt, das die angegebene Anzahl von Einträgen.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|Legt RGB-Werte und Flags in einen Bereich von Einträgen in einer logischen Palette fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|Gibt die `HPALETTE` angefügt werden, um die `CPalette`.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Palette stellt eine Schnittstelle zwischen einer Anwendung und einer Farbe Ausgabegerät (z. B. ein Anzeigegerät). Die Schnittstelle kann die Anwendung Vorteile der die Farbe des Ausgabegeräts voll nutzen zu können, ohne die Farben, die von einer anderen Anwendung stark beeinträchtigen. Windows verwendet die Anwendung logische Palette (eine Liste der erforderlichen Farben) und die Systempalette (die verfügbare Farben definiert) bestimmen die verwendeten Farben an.  
  
 Ein `CPalette` Objekt stellt Memberfunktionen für das Bearbeiten der Palette auf das Objekt verweist. Erstellen Sie ein `CPalette` -Objekt und seine Memberfunktionen verwenden, um der tatsächlichen Palette ein Graphics Device Interface (GDI)-Objekt erstellen und seine Einträge und andere Eigenschaften ändern.  
  
 Weitere Informationen zur Verwendung von `CPalette`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="animatepalette"></a>: CPalette:: AnimatePalette  
 Einträge in der logischen Palette an angefügt ersetzt die `CPalette` Objekt.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartIndex`  
 Gibt den ersten Eintrag in der Palette animiert werden soll.  
  
 `nNumEntries`  
 Gibt die Anzahl der Einträge in der Palette animiert werden soll.  
  
 `lpPaletteColors`  
 Verweist auf das erste Element eines Arrays von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Strukturen ersetzen die Paletteneinträge identifizierten `nStartIndex` und `nNumEntries`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft `AnimatePalette`, hat kein seines Clientbereichs aktualisieren, da Windows sofort die neuen Einträge in der Systempalette zugeordnet.  
  
 Die `AnimatePalette` Funktion ändert nur Einträge mit der **PC_RESERVED** flag festgelegt, in der entsprechenden **PalPaletteEntry** Mitglied der [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) -Struktur, die zugeordnet ist die `CPalette` Objekt. Finden Sie unter **LOGPALETTE** in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu dieser Struktur.  
  
##  <a name="cpalette"></a>CPalette::CPalette  
 Erstellt ein `CPalette`-Objekt.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt hat keine angefügten Palette bis zum Aufruf von `CreatePalette` eine anfügen.  
  
##  <a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette  
 Erstellt eine Halbtonpalette für den Gerätekontext.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Identifiziert den Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Bei der Anwendung sollte erstellt einer Halbtonpalette der streckmodus Gerätekontext festgelegt ist, um **HALBTON**. Zurückgegebene logische Halbtonpalette die [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) Memberfunktion dann ausgewählt und im Gerätekontext vor realisiert das [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) oder [StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) -Funktion aufgerufen wird.  
  
 Finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu `CreateHalftonePalette` und **StretchDIBits**.  
  
##  <a name="createpalette"></a>CPalette::CreatePalette  
 Initialisiert eine `CPalette` -Objekt durch Erstellen einer logischen Windows-Farbpalette und diese an die `CPalette` Objekt.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogPalette`  
 Verweist auf eine [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) -Struktur, die Informationen zu den Farben der logischen Palette enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen zu den **LOGPALETTE** Struktur.  
  
##  <a name="fromhandle"></a>CPalette::FromHandle  
 Gibt einen Zeiger auf ein `CPalette` Objekt, wenn ein Handle zu einer Windows-Palette-Objekt zu erhalten.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `hPalette`  
 Ein Handle für ein Windows-GDI-Farben-Palette.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPalette` -Objekt, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CPalette` Objekt ist noch nicht auf die Windows-Farbpalette, eine temporäre angefügt `CPalette` Objekt erstellt und angefügt wird. Dieser temporäre `CPalette` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner Ereignisschleife aufweist, zu der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht ein Fenster gültig.  
  
##  <a name="getentrycount"></a>CPalette::GetEntryCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der Einträge in einer bestimmten logischen Palette abzurufen.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Einträgen in einer logischen Palette.  
  
##  <a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 Gibt den Index des Eintrags in der logischen Palette, die den Wert der angegebenen Farbe am ehesten entspricht.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Farbe zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index eines Eintrags in einer logische Palette. Der Eintrag enthält die Farbe, die meisten fast mit die angegebene Farbe übereinstimmt.  
  
##  <a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 Ruft einen Bereich der Paletteneinträge in einer logischen Palette ab.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartIndex`  
 Gibt den ersten Eintrag in der logischen Palette abgerufen werden sollen.  
  
 `nNumEntries`  
 Gibt die Anzahl der Einträge in der logischen Palette abgerufen werden sollen.  
  
 `lpPaletteColors`  
 Verweist auf ein Array von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Datenstrukturen die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen Angaben enthalten `nNumEntries`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Einträge, die von der logischen Palette abgerufen; 0, wenn die Funktion ist fehlgeschlagen.  
  
##  <a name="operator_hpalette"></a>CPalette::operator HPALETTE  
 Verwenden Sie diesen Operator zum Abrufen der angefügten Windows GDI-Handle für die `CPalette` Objekt.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPalette` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator ist ein Typumwandlungsoperator verwendet, die direkte Verwendung von unterstützt ein `HPALETTE` Objekt.  
  
 Weitere Informationen zur Verwendung von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="resizepalette"></a>CPalette::ResizePalette  
 Ändert die Größe der logischen Palette an der der `CPalette` Objekt, das die Anzahl von Einträgen, die durch angegebene `nNumEntries`.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumEntries`  
 Gibt die Anzahl der Einträge in der Palette ein, nachdem es Größe geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Palette erfolgreich geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft `ResizePalette` zum Reduzieren der Größe der Palette sind die Einträge in die angepasste Palette verbleiben unverändert. Wenn die Anwendung ruft `ResizePalette` um der Palette zu vergrößern, werden die zusätzlichen Paletteneinträge auf Schwarz (Rot-, Grün- und Blau-Werte sind alle 0) festgelegt, und die Flags für alle zusätzlichen Einträge werden auf 0 festgelegt.  
  
 Weitere Informationen zu den Windows-API- `ResizePalette`, finden Sie unter [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 Legt RGB-Werte und Flags in einen Bereich von Einträgen in einer logischen Palette fest.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartIndex`  
 Gibt den ersten Eintrag in der logischen Palette festgelegt werden.  
  
 `nNumEntries`  
 Gibt die Anzahl der Einträge in der logischen Palette festgelegt werden.  
  
 `lpPaletteColors`  
 Verweist auf ein Array von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Datenstrukturen die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen Angaben enthalten `nNumEntries`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Einträge, die in der logischen Palette festgelegt; 0, wenn die Funktion ist fehlgeschlagen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die logische Palette einen Gerätekontext ausgewählt wird, wenn die Anwendung aufruft, `SetPaletteEntries`, die Änderungen nicht wirksam bis die Anwendung ruft [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Weitere Informationen über die Windows-Struktur **PALETTEENTRY**, finden Sie unter [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)





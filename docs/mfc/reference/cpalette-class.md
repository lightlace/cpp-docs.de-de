---
title: CPalette-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 486338d579f304a6de1a54674a7711bb6c56f38c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cpalette-class"></a>CPalette-Klasse
Kapselt eine Windows-Farbpalette.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|Erstellt eine `CPalette` Objekt mit keine angefügte Windows-Farbpalette. Sie initialisieren müssen die `CPalette` Objekt mit einem der Initialisierung-Memberfunktionen, bevor er verwendet werden kann.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[: CPalette:: AnimatePalette](#animatepalette)|Einträge in der logischen Palette identifizierte ersetzt die `CPalette` Objekt. Die Anwendung verfügt nicht zum Aktualisieren seines Clientbereichs, da Windows sofort die neuen Einträge in der Systempalette zugeordnet.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|Erstellt eine Halbtonpalette für den Gerätekontext und fügt es der `CPalette` Objekt.|  
|[CPalette::CreatePalette](#createpalette)|Erstellt eine Windows-Farbpalette und fügt es der `CPalette` Objekt.|  
|[CPalette::FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CPalette` Objekt, wenn ein Handle zu einem Windows-Palette-Objekt vorhanden.|  
|[CPalette::GetEntryCount](#getentrycount)|Ruft die Anzahl der Paletteneinträge in einer logischen Palette ab.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|Gibt den Index des Eintrags in die logische Palette, die einen Farbwert am ehesten entspricht.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|Ruft einen Bereich von Paletteneinträge in einer logischen Palette ab.|  
|[CPalette::ResizePalette](#resizepalette)|Ändert die Größe der logischen Palette gemäß der `CPalette` Objekt, das die angegebene Anzahl von Einträgen.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|Legt RGB-Werte und Flags in einem Bereich von Einträgen in einer logischen Palette fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPalette::operator HPALETTE](#operator_hpalette)|Gibt die `HPALETTE` angefügt, um die `CPalette`.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Palette stellt eine Schnittstelle zwischen einer Anwendung und eine Farbe Ausgabegerät (z. B. ein Anzeigegerät). Die Schnittstelle kann die Anwendung uneingeschränkt nutzen die Funktionen des Ausgabegeräts ohne Farben angezeigt, die von einer anderen Anwendung schwerwiegend beeinträchtigt. Windows verwendet die Anwendung logische Palette (eine Liste der erforderlichen Farben) und der Systempalette (die verfügbare Farben definiert) bestimmen die verwendeten Farben an.  
  
 Ein `CPalette` Objekt bietet Memberfunktionen für das Bearbeiten der Palette, von dem Objekt bezeichnet. Erstellen einer `CPalette` Objekt und seine Memberfunktionen verwenden, auf die tatsächlichen Palette eines Graphics Device Interface (GDI)-Objekts zu erstellen und Bearbeiten von seiner Einträge und andere Eigenschaften.  
  
 Weitere Informationen zur Verwendung von `CPalette`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="animatepalette"></a>: CPalette:: AnimatePalette  
 Ersetzt die Einträge in der logischen Palette angefügt, um die `CPalette` Objekt.  
  
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
 Gibt die Anzahl von Einträgen in der Palette animiert werden soll.  
  
 `lpPaletteColors`  
 Verweist auf das erste Element eines Arrays von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Strukturen, die die Paletteneinträge identifizierte ersetzen `nStartIndex` und `nNumEntries`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft `AnimatePalette`, er muss nicht in seinen Clientbereich aktualisieren, da Windows sofort die neuen Einträge in der Systempalette zugeordnet.  
  
 Die `AnimatePalette` Funktion ändert sich nur auf die Einträge mit der **PC_RESERVED** flag festgelegt, in der entsprechenden **PalPaletteEntry** Mitglied der [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) Struktur angefügte der `CPalette` Objekt. Finden Sie unter **LOGPALETTE** in das Windows SDK für Weitere Informationen zu dieser Struktur.  
  
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
 Eine Anwendung sollte eine Halbtonpalette erstellen, wenn der streckmodus des einen Gerätekontext, um festgelegt ist **RASTERBILD**. Die logische Halbtonpalette zurückgegebenes der [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) Memberfunktion dann ausgewählt und in den Gerätekontext vor realisiert der [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) oder [ StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) Funktion aufgerufen wird.  
  
 Finden Sie im Windows-SDK für Weitere Informationen zu `CreateHalftonePalette` und **StretchDIBits**.  
  
##  <a name="createpalette"></a>CPalette::CreatePalette  
 Initialisiert eine `CPalette` Objekt, indem Sie eine logische Windows-Farbpalette erstellen und Anfügen von es die `CPalette` Objekt.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `lpLogPalette`  
 Verweist auf eine [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) -Struktur, die Informationen über die Farben in der logischen Palette enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie im Windows-SDK für Weitere Informationen zu den **LOGPALETTE** Struktur.  
  
##  <a name="fromhandle"></a>CPalette::FromHandle  
 Gibt einen Zeiger auf ein `CPalette` Objekt, wenn ein Handle zu einem Windows-Palette-Objekt vorhanden.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>Parameter  
 `hPalette`  
 Ein Handle für eine Windows-GDI-Farbpalette.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CPalette` -Objekt, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CPalette` Objekt noch nicht auf die Windows-Farbpalette, ein temporäres angefügt `CPalette` Objekt erstellt und angefügt. Dieser temporäre `CPalette` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Leerlaufzeit in seiner-Ereignisschleife aufweist, zu dem alle temporären Grafik Zeit Objekte gelöscht werden. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht von einem Fenster gültig.  
  
##  <a name="getentrycount"></a>CPalette::GetEntryCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Einträge in einer bestimmten logischen Palette an.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Einträgen in einer logischen Palette.  
  
##  <a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 Gibt den Index des Eintrags in die logische Palette, die den Wert der angegebenen Farbe am ehesten entspricht.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `crColor`  
 Gibt die Farbe, die abgeglichen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index eines Eintrags in einer logischen Palette. Der Eintrag enthält, die Farbe, die am häufigsten fast übereinstimmen, die die angegebene Farbe.  
  
##  <a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 Ruft einen Bereich von Paletteneinträge in einer logischen Palette ab.  
  
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
 Gibt die Anzahl von Einträgen in der logischen Palette abgerufen werden sollen.  
  
 `lpPaletteColors`  
 Verweist auf ein Array von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Datenstrukturen, die die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen Angaben enthalten `nNumEntries`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Einträgen, die aus der logischen Palette abgerufen; 0, wenn Fehler bei der Funktion.  
  
##  <a name="operator_hpalette"></a>CPalette::operator HPALETTE  
 Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle Abrufen der `CPalette` Objekt.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CPalette` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator wird ein Typumwandlungsoperator, die direkte Verwendung von unterstützt ein `HPALETTE` Objekt.  
  
 Weitere Informationen zum Verwenden von Grafikobjekten, finden Sie im Artikel [Grafik Objekte](http://msdn.microsoft.com/library/windows/desktop/dd144962) im Windows SDK.  
  
##  <a name="resizepalette"></a>CPalette::ResizePalette  
 Ändert die Größe der logische Palette angefügt, um die `CPalette` Objekt, das die Anzahl von Einträgen, die vom angegebenen `nNumEntries`.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumEntries`  
 Gibt die Anzahl von Einträgen in der Palette, nachdem es geändert wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Palette erfolgreich geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft `ResizePalette` zum Reduzieren der Größe der Palette, werden die Einträge in der geänderten Größe Palette verbleibende unverändert. Wenn die Anwendung aufruft, `ResizePalette` die Palette zu vergrößern, werden die zusätzlichen Paletteneinträge auf Schwarz (Rot-, Grün- und Blau-Werte sind alle 0) festgelegt, und die Flags für alle weiteren Einträge auf 0 festgelegt sind.  
  
 Weitere Informationen zur Windows-API `ResizePalette`, finden Sie unter [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) im Windows SDK.  
  
##  <a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 Legt RGB-Werte und Flags in einem Bereich von Einträgen in einer logischen Palette fest.  
  
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
 Gibt die Anzahl von Einträgen in der logischen Palette festgelegt werden.  
  
 `lpPaletteColors`  
 Verweist auf ein Array von [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Datenstrukturen, die die Paletteneinträge zu erhalten. Das Array muss mindestens so viele Datenstrukturen Angaben enthalten `nNumEntries`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Einträgen, die in der logischen Palette festgelegt; 0, wenn Fehler bei der Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die logische Palette einen Gerätekontext ausgewählt ist, wenn die Anwendung aufruft, `SetPaletteEntries`, werden die Änderungen nicht wirksam bis die Anwendung ruft [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette).  
  
 Weitere Informationen zu den Windows-Struktur **PALETTEENTRY**, finden Sie unter [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)




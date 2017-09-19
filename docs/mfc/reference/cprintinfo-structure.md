---
title: CPrintInfo-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ffa72acc58e0ac1a387e67e6542abcd466be9640
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cprintinfo-structure"></a>CPrintInfo-Struktur
Speichert Informationen zu einem Auftrag drucken oder Seitenansicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Gibt die Anzahl der ersten Seite gedruckt wird.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Gibt die Anzahl der letzten Seite des Dokuments.|  
|[CPrintInfo::GetMinPage](#getminpage)|Gibt die Nummer der ersten Seite des Dokuments zurück.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Gibt die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject Druckauftrag gedruckt wird.|  
|[CPrintInfo::GetToPage](#gettopage)|Gibt die Anzahl der letzten Seite gedruckt wird.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Legt die Anzahl der letzten Seite des Dokuments.|  
|[CPrintInfo::SetMinPage](#setminpage)|Legt die Anzahl der ersten Seite des Dokuments.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Enthält ein Flag gibt an, ob das Framework die Druckschleife fortgesetzt werden soll.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Enthält ein Flag gibt an, ob das Dokument direkt (ohne das Dialogfeld Drucken) gedruckt wird.|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Enthält ein Flag an, ob das zu druckende Dokument DocObject ist.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Enthält ein Flag gibt an, ob das Dokument wird in der Vorschau angezeigt wird.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|Gibt Vorgänge an DocObject drucken.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Enthält einen Zeiger auf eine Struktur Benutzer erstellt.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Gibt die Anzahl der gegenwärtig gedruckte Seite.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Gibt die Projektnummer, die vom Betriebssystem für den aktuellen Auftrag zugewiesen|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Identifiziert die Anzahl der Seiten, die im Vorschaufenster angezeigt. 1 oder 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Gibt Offset der ersten Seite einer bestimmten DocObject in einen kombinierten DocObject Druckauftrag.|  
|[CPrintInfo::m_pPD](#m_ppd)|Enthält einen Zeiger auf die `CPrintDialog` für das Dialogfeld Drucken verwendete Objekt.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Gibt ein Rechteck, das die aktuellen nutzbaren Seitenbereich definieren.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Enthält eine Zeichenfolge für die Seitenzahl Anzeige.|  
  
## <a name="remarks"></a>Hinweise  
 `CPrintInfo`ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Das Framework erstellt ein Objekt der `CPrintInfo` jedes Mal, wenn das Drucken oder Seitenansicht ausgewählt, und es zerstört, wenn der Befehl abgeschlossen wird.  
  
 `CPrintInfo`enthält Informationen über den Auftrag als Ganzes, wie z. B. den Bereich der Seiten, die gedruckt werden, und den aktuellen Status des Druckauftrags, z. B. die gerade gedruckte Seite. Einige Informationen in einem zugeordneten [CPrintDialog](../../mfc/reference/cprintdialog-class.md) -Objekt dieses Objekt enthält die vom Benutzer im Dialogfeld Drucken eingegebenen Werte.  
  
 Ein `CPrintInfo` Objekt zwischen dem Framework und der Ansichtsklasse übergeben wird, die während des Druckvorgangs und wird verwendet, um den Austausch von Informationen zwischen den beiden. Beispielsweise das Framework informiert der Ansichtsklasse welche Seite des Dokuments zu drucken, indem Sie einen Wert zuweisen der `m_nCurPage` Mitglied `CPrintInfo`; die Sicht-Klasse ruft den Wert ab und führt das eigentliche Drucken der angegebenen Seite.  
  
 Ein weiteres Beispiel ist der Fall, in dem die Länge des Dokuments nicht bekannt ist, bis es gedruckt wird. In diesem Fall überprüft die Ansichtsklasse für das Ende des Dokuments jedes Mal, wenn eine Seite gedruckt wird. Die View-Klasse legt fest, wenn das Ende erreicht ist, die `m_bContinuePrinting` Mitglied `CPrintInfo` auf **FALSE**; dieser informiert, dass das Framework um die Druckschleife beendet.  
  
 `CPrintInfo`wird verwendet, indem Sie die Memberfunktionen von `CView` aufgelistet unter "Siehe auch". Weitere Informationen zu der von der Microsoft Foundation Class-Bibliothek bereitgestellten Druckarchitektur, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md) und [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) und in den Artikeln [Drucken](../../mfc/printing.md) und [drucken: mehrseitige Dokumente](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPrintInfo`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="getfrompage"></a>CPrintInfo::GetFromPage  
 Rufen Sie diese Funktion zum Abrufen der Nummer der ersten Seite gedruckt werden.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ersten Seite gedruckt werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Wert, der vom Benutzer im Dialogfeld Drucken angegeben und befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist die Standardeinstellung der ersten Seite des Dokuments.  
  
##  <a name="getmaxpage"></a>CPrintInfo::GetMaxPage  
 Rufen Sie diese Funktion, um die Anzahl der letzten Seite des Dokuments abgerufen.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der letzten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt, auf die `m_pPD` Member.  
  
##  <a name="getminpage"></a>CPrintInfo::GetMinPage  
 Rufen Sie diese Funktion, um die Anzahl der ersten Seite des Dokuments abgerufen.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ersten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt, auf die `m_pPD` Member.  
  
##  <a name="getoffsetpage"></a>CPrintInfo::GetOffsetPage  
 Rufen Sie diese Funktion zum Abrufen des Offsets mehrere DocObject-Elemente von einem Client DocObject drucken.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject Druckauftrag gedruckt wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert verweist auf die **M_nOffsetPage** Element. Die erste Seite des Dokuments werden fortlaufend die **M_nOffsetPage** Wert + 1 DocObject mit anderen aktiven Dokumenten gedruckt. Die **M_nOffsetPage** Mitglied gilt nur, wenn die **M_bDocObject** Wert **TRUE**.  
  
##  <a name="gettopage"></a>CPrintInfo::GetToPage  
 Rufen Sie diese Funktion zum Abrufen der Nummer der letzten Seite gedruckt werden.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der letzten Seite gedruckt werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Wert, der vom Benutzer im Dialogfeld Drucken angegeben und befindet sich in der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist die Standardeinstellung der letzten Seite des Dokuments.  
  
##  <a name="m_bcontinueprinting"></a>CPrintInfo::m_bContinuePrinting  
 Enthält ein Flag gibt an, ob das Framework die Druckschleife fortgesetzt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie Druckzeit durchführen, stellen Sie dieses Element auf **FALSE** in der Überschreibung der `CView::OnPrepareDC` nach das Ende des Dokuments erreicht wurde. Sie brauchen diese Variable ändern, wenn Sie die Länge des Dokuments zu Beginn des Druckauftrags mit angegeben haben die `SetMaxPage` Member-Funktion. Die `m_bContinuePrinting` Element ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_bdirect"></a>CPrintInfo::m_bDirect  
 Das Framework wird dieser Member auf **TRUE** , wenn das Dialogfeld Drucken für direct-Druck, umgangen werden kann **FALSE** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Drucken wird normalerweise umgangen, beim Drucken von der Shell oder beim Drucken erfolgt mithilfe der Befehls-ID **ID_FILE_PRINT_DIRECT**.  
  
 Sie normalerweise bei diesem Member nicht ändern, aber wenn Sie ändern, ändern Sie ihn vor dem Aufruf [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) in der Überschreibung der [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="m_bdocobject"></a>CPrintInfo::m_bDocObject  
 Enthält ein Flag an, ob das zu druckende Dokument DocObject ist.  
  
### <a name="remarks"></a>Hinweise  
 Datenmember `m_dwFlags` und **M_nOffsetPage** ungültig sind, es sei denn, dieses Flag **TRUE**.  
  
##  <a name="m_bpreview"></a>CPrintInfo::m_bPreview  
 Enthält ein Flag gibt an, ob das Dokument wird in der Vorschau angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird vom Framework festgelegt, je nachdem, welche die Benutzer-Befehl ausgeführt. Das Dialogfeld Drucken wird nicht für einen Auftrag Seitenansicht angezeigt. Die **M_bPreview** Element ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_dwflags"></a>CPrintInfo::m_dwFlags  
 Enthält eine Kombination von Flags, Drucken DocObject-Vorgänge angibt.  
  
### <a name="remarks"></a>Hinweise  
 Nur gültig, wenn Datenmember **M_bDocObject** ist **TRUE**.  
  
 Die Flags können eine oder mehrere der folgenden Werte sein:  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>CPrintInfo::m_lpUserData  
 Enthält einen Zeiger auf eine Struktur Benutzer erstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können dies um Drucken-spezifische Daten zu speichern, die nicht in der Ansichtsklasse gespeichert werden sollen. Die **M_lpUserData** Element ist eine öffentliche Variable des Typs **LPVOID**.  
  
##  <a name="m_ncurpage"></a>CPrintInfo::m_nCurPage  
 Enthält die Anzahl der aktuellen Seite.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft `CView::OnPrepareDC` und `CView::OnPrint` einmal für jede Seite des Dokuments ein, geben Sie einen anderen Wert für dieses Element jedes Mal; die Werte reichen von der von zurückgegebene Wert `GetFromPage` von zurückgegebenen `GetToPage`. Verwenden Sie diesen Member in den Außerkraftsetzungen von `CView::OnPrepareDC` und `CView::OnPrint` die angegebene Seite des Dokuments gedruckt.  
  
 Wenn im Vorschaumodus erstmalig aufgerufen wird, liest das Framework den Wert des Elements zu bestimmen, welche Seite des Dokuments zunächst in der Vorschau angezeigt werden soll. Sie können den Wert dieses Elements festlegen, in der Überschreibung der `CView::OnPreparePrinting` die aktuelle Position im Dokument des Benutzers beibehalten werden soll, wenn im Vorschaumodus eingeben. Die `m_nCurPage` Element ist eine öffentliche Variable des Typs **UINT**.  
  
##  <a name="m_njobnumber"></a>CPrintInfo::m_nJobNumber  
 Gibt die Projektnummer, die vom Betriebssystem für den aktuellen Auftrag zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert ist möglicherweise **SP_ERROR** Wenn der Auftrag noch ausgedruckt noch nicht (d. h., wenn der `CPrintInfo` Objekt wird neu erstellt und noch nicht zum Drucken verwendet), oder wenn beim Starten des Auftrags ein Fehler aufgetreten.  
  
##  <a name="m_nnumpreviewpages"></a>CPrintInfo::m_nNumPreviewPages  
 Enthält die Anzahl der Seiten, die in der Vorschau angezeigt. Sie können 1 oder 2 sein.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_nNumPreviewPages** Element ist eine öffentliche Variable des Typs **UINT**.  
  
##  <a name="m_noffsetpage"></a>CPrintInfo::m_nOffsetPage  
 Enthält die Anzahl der Seiten, die vor der ersten Seite des bestimmten DocObject in einem kombinierten DocObject Druckauftrag.  
  
##  <a name="m_ppd"></a>CPrintInfo::m_pPD  
 Enthält einen Zeiger auf die `CPrintDialog` Objekt verwendet, um das Dialogfeld "Drucken" für den Auftrag anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Die `m_pPD` Element ist eine öffentliche Variable deklariert, die als Zeiger auf `CPrintDialog`.  
  
##  <a name="m_rectdraw"></a>CPrintInfo::m_rectDraw  
 Gibt den verwendbaren Zeichenbereich der Seite in logischen Koordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Sie möchten in der Überschreibung der finden Sie unter diesem `CView::OnPrint`. Bei diesem Member können zum Nachverfolgen von welchem Bereich nutzbar bleibt, nachdem Sie Kopfzeilen, Fußzeilen und So weiter drucken. Die **M_rectDraw** Element ist eine öffentliche Variable des Typs `CRect`.  
  
##  <a name="m_strpagedesc"></a>CPrintInfo::m_strPageDesc  
 Enthält eine Formatzeichenfolge, die zum Anzeigen von Seitenzahlen Seitenansicht verwendet. Diese Zeichenfolge besteht aus zwei Teilzeichenfolgen, eine einzelne Seite angezeigt und eine Double-Seite angezeigt werden, jeweils durch das Zeichen "\n" beendet.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet "Seite %u\nPages % u-%u\n" als Standardwert. Wenn Sie ein anderes Format für die Seitenzahlen möchten, geben Sie eine Formatzeichenfolge, in der Überschreibung der `CView::OnPreparePrinting`. Die **M_strPageDesc** Element ist eine öffentliche Variable des Typs `CString`.  
  
##  <a name="setmaxpage"></a>CPrintInfo::SetMaxPage  
 Rufen Sie diese Funktion zum Angeben der Anzahl der letzten Seite des Dokuments.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Parameter  
 *nMaxPage*  
 Die Anzahl der letzten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt, auf die `m_pPD` Member. Wenn die Länge des Dokuments bekannt ist, bevor es gedruckt wird, rufen Sie diese Funktion aus der Überschreibung der `CView::OnPreparePrinting`. Wenn die Länge des Dokuments vom Benutzer im Dialogfeld Drucken angegebene Einstellung abhängig ist, rufen Sie diese Funktion aus der Überschreibung der `CView::OnBeginPrinting`. Wenn die Länge des Dokuments nicht bekannt ist, bevor es gedruckt wird, verwenden Sie die `m_bContinuePrinting` Member zum Steuern der drucken-Schleife.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="setminpage"></a>CPrintInfo::SetMinPage  
 Rufen Sie diese Funktion zum Angeben der Anzahl der ersten Seite des Dokuments.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Parameter  
 *nMinPage*  
 Die Nummer der ersten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Seitenzahlen beginnen normalerweise mit 1. Dieser Wert wird gespeichert, der `CPrintDialog` Objekt, auf die `m_pPD` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)





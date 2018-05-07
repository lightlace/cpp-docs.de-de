---
title: CPrintInfo-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPrintInfo
dev_langs:
- C++
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1da952e14158ab92d888a703aa8451c0ca39406
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cprintinfo-structure"></a>CPrintInfo-Struktur
Speichert Informationen zu einem Auftrag drucken oder Seitenansicht an.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CPrintInfo  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](#getfrompage)|Gibt die Anzahl der ersten Seite gedruckt wird.|  
|[CPrintInfo::GetMaxPage](#getmaxpage)|Gibt die Anzahl der letzten Seite des Dokuments zurück.|  
|[CPrintInfo::GetMinPage](#getminpage)|Gibt die Anzahl der ersten Seite des Dokuments zurück.|  
|[CPrintInfo::GetOffsetPage](#getoffsetpage)|Gibt die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject Druckauftrag gedruckt wird.|  
|[CPrintInfo::GetToPage](#gettopage)|Gibt die Anzahl der letzten Seite gedruckt wird.|  
|[CPrintInfo::SetMaxPage](#setmaxpage)|Legt die Anzahl der letzten Seite des Dokuments.|  
|[CPrintInfo::SetMinPage](#setminpage)|Legt die Anzahl der ersten Seite des Dokuments.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintInfo::m_bContinuePrinting](#m_bcontinueprinting)|Enthält ein Flag, das angibt, ob das Framework das Drucken-Schleife fortgesetzt werden soll.|  
|[CPrintInfo::m_bDirect](#m_bdirect)|Enthält ein Flag, das angibt, ob das Dokument direkt (ohne Anzeige des Dialogfelds drucken) gedruckt wird.|  
|[CPrintInfo::m_bDocObject](#m_bdocobject)|Enthält ein Flag, das angibt, ob das Dokument drucken DocObject ist.|  
|[CPrintInfo::m_bPreview](#m_bpreview)|Enthält ein Flag, das angibt, ob das Dokument wird in der Vorschau angezeigt wird.|  
|[CPrintInfo::m_dwFlags](#m_dwflags)|Gibt Vorgänge an DocObject drucken.|  
|[CPrintInfo::m_lpUserData](#m_lpuserdata)|Enthält einen Zeiger auf eine Struktur Benutzer erstellt.|  
|[CPrintInfo::m_nCurPage](#m_ncurpage)|Gibt die Anzahl der gegenwärtig gedruckte Seite.|  
|[CPrintInfo::m_nJobNumber](#m_njobnumber)|Gibt die vom Betriebssystem für den aktuellen Druckauftrag zugewiesene Auftrag-Nummer|  
|[CPrintInfo::m_nNumPreviewPages](#m_nnumpreviewpages)|Identifiziert die Anzahl der Seiten, die im Vorschaufenster angezeigt. 1 oder 2.|  
|[CPrintInfo::m_nOffsetPage](#m_noffsetpage)|Gibt den Offset der ersten Seite von einem bestimmten DocObject in einem kombinierten DocObject Druckauftrag an.|  
|[CPrintInfo::m_pPD](#m_ppd)|Enthält einen Zeiger auf die `CPrintDialog` für des Dialogfelds drucken verwendete Objekt.|  
|[CPrintInfo::m_rectDraw](#m_rectdraw)|Gibt ein Rechteck, das den aktuellen nutzbaren Seitenbereich definieren.|  
|[CPrintInfo::m_strPageDesc](#m_strpagedesc)|Enthält eine Formatzeichenfolge für die Seitenzahl Anzeige.|  
  
## <a name="remarks"></a>Hinweise  
 `CPrintInfo` ist eine Struktur, und verfügt nicht über eine Basisklasse.  
  
 Das Framework erstellt ein Objekt vom `CPrintInfo` jedes Mal, wenn das Drucken oder Befehl "Seitenansicht" ausgewählt ist, und es zerstört, wenn der Befehl abgeschlossen ist.  
  
 `CPrintInfo` enthält Informationen zu den Druckauftrag als Ganzes, wie z. B. den Bereich der Seiten, die gedruckt werden soll, und der aktuelle Status des Druckauftrags, z. B. die gerade gedruckte Seite. Einige Informationen befindet sich in einem zugeordneten [CPrintDialog](../../mfc/reference/cprintdialog-class.md) Objekt; dieses Objekt enthält die vom Benutzer in das Dialogfeld Drucken eingegebenen Werte.  
  
 Ein `CPrintInfo` Objekt zwischen dem Framework und die View-Klasse übergeben wird, die während des Druckvorgangs und wird verwendet, um Informationen zwischen den beiden austauschen. Beispielsweise das Framework informiert Ansichtsklasse welcher Seite des Dokuments durch Zuweisen eines Werts zum Drucken der `m_nCurPage` Mitglied `CPrintInfo`; die Klasse ruft den Wert ab, und führt das eigentliche Drucken der angegebenen Seite anzuzeigen.  
  
 Ein weiteres Beispiel ist der Fall, in dem die Länge des Dokuments nicht bekannt ist, bis es gedruckt wird. In diesem Fall überprüft der Ansichtsklasse für das Ende des Dokuments jedes Mal, wenn eine Seite gedruckt wird. Beim Erreichen des Endes der Ansichtsklasse legt die `m_bContinuePrinting` Mitglied `CPrintInfo` auf **"false"**; dies informiert, dass das Framework um Drucken-Schleife zu beenden.  
  
 `CPrintInfo` wird verwendet, indem Sie die Memberfunktionen von `CView` aufgelistet unter "Siehe auch". Weitere Informationen zu den drucken Architektur, die von der Microsoft Foundation Class-Bibliothek bereitgestellt, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md) und [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md) sowie in den Artikeln [ Drucken von](../../mfc/printing.md) und [drucken: mehrseitige Dokumente](../../mfc/multipage-documents.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPrintInfo`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="getfrompage"></a>  CPrintInfo::GetFromPage  
 Mit dieser Funktion wird zum Abrufen der Anzahl der ersten Seite gedruckt werden.  
  
```  
UINT GetFromPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ersten Seite gedruckt werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Wert, der vom Benutzer im Dialogfeld "Drucken" angegeben und befindet sich in der `CPrintDialog` Objekt verweist die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist die Standardeinstellung der ersten Seite des Dokuments an.  
  
##  <a name="getmaxpage"></a>  CPrintInfo::GetMaxPage  
 Mit dieser Funktion wird zum Abrufen der Anzahl der letzten Seite des Dokuments.  
  
```  
UINT GetMaxPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der letzten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt verweist die `m_pPD` Member.  
  
##  <a name="getminpage"></a>  CPrintInfo::GetMinPage  
 Mit dieser Funktion wird zum Abrufen der Anzahl der ersten Seite des Dokuments.  
  
```  
UINT GetMinPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ersten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt verweist die `m_pPD` Member.  
  
##  <a name="getoffsetpage"></a>  CPrintInfo::GetOffsetPage  
 Mit dieser Funktion wird zum Abrufen des Offsets, mehrere DocObject-Elemente von einem Client DocObject drucken.  
  
```  
UINT GetOffsetPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Seiten, die vor der ersten Seite eines DocObject-Elements in einem kombinierten DocObject Druckauftrag gedruckt wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert verweist auf die **M_nOffsetPage** Member. Die erste Seite des Dokuments wird automatisch die **M_nOffsetPage** Wert + 1 als DocObject mit anderen aktive Dokumente gedruckt. Die **M_nOffsetPage** Element gilt nur, wenn die **M_bDocObject** Wert ist **"true"**.  
  
##  <a name="gettopage"></a>  CPrintInfo::GetToPage  
 Mit dieser Funktion wird zum Abrufen der Anzahl der letzten Seite gedruckt werden.  
  
```  
UINT GetToPage() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der letzten Seite gedruckt werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Wert, der vom Benutzer im Dialogfeld "Drucken" angegeben und befindet sich in der `CPrintDialog` Objekt verweist die `m_pPD` Member. Wenn der Benutzer einen Wert nicht angegeben, ist die Standardeinstellung der letzten Seite des Dokuments an.  
  
##  <a name="m_bcontinueprinting"></a>  CPrintInfo::m_bContinuePrinting  
 Enthält ein Flag, das angibt, ob das Framework das Drucken-Schleife fortgesetzt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das Drucken-Time-Paginierung durchführen, legen Sie bei diesem Member auf **"false"** in der Überschreibung der `CView::OnPrepareDC` nach das Ende des Dokuments erreicht wird. Sie müssen keine dieser Variablen ändern, wenn Sie die Länge des Dokuments am Anfang des Druckauftrags mit angegeben haben die `SetMaxPage` Memberfunktion. Die `m_bContinuePrinting` Member ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_bdirect"></a>  CPrintInfo::m_bDirect  
 Das Framework wird bei diesem Member auf **"true"** , wenn das Dialogfeld Drucken für Direktdruck; umgangen werden kann **"False"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Drucken wird normalerweise umgangen, beim Drucken von der Shell oder beim Drucken erfolgt mithilfe der Befehls-ID **ID_FILE_PRINT_DIRECT**.  
  
 Sie normalerweise bei diesem Member nicht ändern, aber wenn Sie ändern, ändern Sie ihn vor dem Aufruf [CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting) in der Überschreibung der [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="m_bdocobject"></a>  CPrintInfo::m_bDocObject  
 Enthält ein Flag, das angibt, ob das Dokument drucken DocObject ist.  
  
### <a name="remarks"></a>Hinweise  
 Datenmember `m_dwFlags` und **M_nOffsetPage** sind ungültig, es sei denn, dieses Flag ist **"true"**.  
  
##  <a name="m_bpreview"></a>  CPrintInfo::m_bPreview  
 Enthält ein Flag, das angibt, ob das Dokument wird in der Vorschau angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird durch das Framework festgelegt, je nachdem, welche die Benutzer-Befehl ausgeführt. Das Dialogfeld "Drucken" wird nicht für einen Auftrag für die Seitenansicht angezeigt. Die **M_bPreview** Member ist eine öffentliche Variable des Typs **BOOL**.  
  
##  <a name="m_dwflags"></a>  CPrintInfo::m_dwFlags  
 Enthält eine Kombination von Flags DocObject drucken Vorgänge angeben.  
  
### <a name="remarks"></a>Hinweise  
 Nur gültig, wenn Datenmember **M_bDocObject** ist **"true"**.  
  
 Die Flags können eine oder mehrere der folgenden Werte sein:  
  
- **PRINTFLAG_MAYBOTHERUSER**  
  
- **PRINTFLAG_PROMPTUSER**  
  
- **PRINTFLAG_USERMAYCHANGEPRINTER**  
  
- **PRINTFLAG_RECOMPOSETODEVICE**  
  
- **PRINTFLAG_DONTACTUALLYPRINT**  
  
- **PRINTFLAG_FORCEPROPERTIES**  
  
- **PRINTFLAG_PRINTTOFILE**  
  
##  <a name="m_lpuserdata"></a>  CPrintInfo::m_lpUserData  
 Enthält einen Zeiger auf eine Struktur Benutzer erstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese verwenden, zum Drucken-spezifische Daten zu speichern, die nicht in Ihrer Ansichtsklasse gespeichert werden sollen. Die **M_lpUserData** Member ist eine öffentliche Variable des Typs **LPVOID**.  
  
##  <a name="m_ncurpage"></a>  CPrintInfo::m_nCurPage  
 Enthält die Anzahl der aktuellen Seite.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft `CView::OnPrepareDC` und `CView::OnPrint` einmal für jede Seite des Dokuments ein, geben Sie einen anderen Wert für diesen Member jedes Mal; die Werte liegen zwischen den Rückgabewert von `GetFromPage` vom zurückgegebenen `GetToPage`. Verwenden Sie diesen Member in die Außerkraftsetzungen von `CView::OnPrepareDC` und `CView::OnPrint` die angegebene Seite des Dokuments gedruckt.  
  
 Wenn im Vorschaumodus erstmalig aufgerufen wird, liest das Framework den Wert des Elements zu ermitteln, welche Seite des Dokuments anfänglich in der Vorschau angezeigt werden soll. Können, legen Sie den Wert dieses Elements in der Überschreibung der `CView::OnPreparePrinting` für den aktuellen Position im Dokument des Benutzers Unterhalt im Vorschaumodus eingeben. Die `m_nCurPage` Member ist eine öffentliche Variable des Typs **"uint"**.  
  
##  <a name="m_njobnumber"></a>  CPrintInfo::m_nJobNumber  
 Gibt die Auftrag-Anzahl, die vom Betriebssystem für den aktuellen Druckauftrag zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert möglicherweise **SP_ERROR** , wenn der Auftrag noch gedruckt wurde nicht (d. h., wenn die `CPrintInfo` Objekt wird neu erstellt und noch nicht zum Drucken verwendet), oder wenn beim Starten des Auftrags ein Fehler aufgetreten.  
  
##  <a name="m_nnumpreviewpages"></a>  CPrintInfo::m_nNumPreviewPages  
 Enthält die Anzahl der Seiten, die im Vorschaumodus angezeigt. Sie können 1 oder 2 sein.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_nNumPreviewPages** Member ist eine öffentliche Variable des Typs **"uint"**.  
  
##  <a name="m_noffsetpage"></a>  CPrintInfo::m_nOffsetPage  
 Enthält die Anzahl der Seiten, die vor der ersten Seite des einer bestimmten DocObject in einem kombinierten DocObject Druckauftrag an.  
  
##  <a name="m_ppd"></a>  CPrintInfo::m_pPD  
 Enthält einen Zeiger auf die `CPrintDialog` Objekt verwendet, um das Dialogfeld "Drucken" für den Auftrag anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
 Die `m_pPD` Member ist eine öffentliche Variable deklariert, die als Zeiger auf `CPrintDialog`.  
  
##  <a name="m_rectdraw"></a>  CPrintInfo::m_rectDraw  
 Gibt den verwendbaren Zeichnungsbereich Rand der Seite in logischen Koordinaten an.  
  
### <a name="remarks"></a>Hinweise  
 Sie möchten zu diesem finden Sie in der Überschreibung der `CView::OnPrint`. Sie können bei diesem Member verwenden, zum Nachverfolgen von welchem Bereich nutzbar bleibt, nachdem Sie Kopfzeilen, Fußzeilen und So weiter drucken. Die **M_rectDraw** Member ist eine öffentliche Variable des Typs `CRect`.  
  
##  <a name="m_strpagedesc"></a>  CPrintInfo::m_strPageDesc  
 Enthält eine Formatzeichenfolge verwendet, um die Seitenzahlen der Seitenansicht angezeigt. Diese Zeichenfolge besteht aus beiden Teilzeichenfolgen, eine für Einzelseiten-Anzeige und für Double-Seite angezeigt, jeweils durch ein "\n"-Zeichen beendet.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework wird "Seite %u\nPages % u-%u\n" als Standardwert verwendet. Wenn Sie ein anderes Format für die Seitenzahlen möchten, geben Sie eine Formatzeichenfolge, in der Überschreibung der `CView::OnPreparePrinting`. Die **M_strPageDesc** Member ist eine öffentliche Variable des Typs `CString`.  
  
##  <a name="setmaxpage"></a>  CPrintInfo::SetMaxPage  
 Mit dieser Funktion wird zum Angeben der Anzahl der letzten Seite des Dokuments.  
  
```  
void SetMaxPage(UINT nMaxPage);
```  
  
### <a name="parameters"></a>Parameter  
 *nMaxPage*  
 Die Anzahl der letzten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird gespeichert, der `CPrintDialog` Objekt verweist die `m_pPD` Member. Wenn die Länge des Dokuments bekannt ist, bevor es gedruckt wird, rufen Sie diese Funktion aus der Außerkraftsetzung von `CView::OnPreparePrinting`. Wenn die Länge des Dokuments auf eine vom Benutzer im Dialogfeld "Drucken" angegebene Einstellung abhängig ist, rufen Sie diese Funktion aus der Außerkraftsetzung von `CView::OnBeginPrinting`. Wenn die Länge des Dokuments nicht bekannt ist, bis es gedruckt wird, verwenden Sie die `m_bContinuePrinting` Member zum Steuern der drucken-Schleife.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting).  
  
##  <a name="setminpage"></a>  CPrintInfo::SetMinPage  
 Mit dieser Funktion wird zum Angeben der Anzahl der ersten Seite des Dokuments.  
  
```  
void SetMinPage(UINT nMinPage);
```  
  
### <a name="parameters"></a>Parameter  
 *nMinPage*  
 Die Anzahl der ersten Seite des Dokuments.  
  
### <a name="remarks"></a>Hinweise  
 Seitenzahlen beginnt normalerweise bei 1. Dieser Wert wird gespeichert, der `CPrintDialog` Objekt verweist die `m_pPD` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)   
 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)   
 [CView::OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)   
 [CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)   
 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)   
 [CView::OnPrint](../../mfc/reference/cview-class.md#onprint)




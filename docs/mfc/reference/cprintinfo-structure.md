---
title: "CPrintInfo Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo structure"
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPrintInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert Informationen über einen Drucks\- oder Seitenansichtsauftrag.  
  
## Syntax  
  
```  
struct CPrintInfo  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintInfo::GetFromPage](../Topic/CPrintInfo::GetFromPage.md)|Gibt die Nummer der ersten Seite zurück, die gedruckt wird.|  
|[CPrintInfo::GetMaxPage](../Topic/CPrintInfo::GetMaxPage.md)|Gibt die Nummer der letzten Seite des Dokuments zurück.|  
|[CPrintInfo::GetMinPage](../Topic/CPrintInfo::GetMinPage.md)|Gibt die Nummer der ersten Seite des Dokuments zurück.|  
|[CPrintInfo::GetOffsetPage](../Topic/CPrintInfo::GetOffsetPage.md)|Gibt die Anzahl der Seiten zurück, die der ersten Seite eines DocObject\-Elements vorausgehen, das in einem kombinierten DocObject\-Druckauftrag gedruckt wird.|  
|[CPrintInfo::GetToPage](../Topic/CPrintInfo::GetToPage.md)|Gibt die Nummer der letzten Seite zurück, die gedruckt wird.|  
|[CPrintInfo::SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)|Legt die Nummer der letzten Seite des Dokuments fest.|  
|[CPrintInfo::SetMinPage](../Topic/CPrintInfo::SetMinPage.md)|Legt die Nummer der ersten Seite des Dokuments fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPrintInfo::m\_bContinuePrinting](../Topic/CPrintInfo::m_bContinuePrinting.md)|Enthält ein Flag, ob das Framework die Drucksschleife fortsetzen sollte.|  
|[CPrintInfo::m\_bDirect](../Topic/CPrintInfo::m_bDirect.md)|Enthält ein Flag, ob das Dokument direkt gedruckt wird \(ohne das Drucken anzuzeigen\).|  
|[CPrintInfo::m\_bDocObject](../Topic/CPrintInfo::m_bDocObject.md)|Enthält ein Flag, das angibt, ob das Dokument, das gedruckt wird, ein DocObject ist.|  
|[CPrintInfo::m\_bPreview](../Topic/CPrintInfo::m_bPreview.md)|Enthält ein Flag, ob das Dokument in der Vorschau angezeigt wird.|  
|[CPrintInfo::m\_dwFlags](../Topic/CPrintInfo::m_dwFlags.md)|Gibt DocObject\-Drucksvorgänge an.|  
|[CPrintInfo::m\_lpUserData](../Topic/CPrintInfo::m_lpUserData.md)|Enthält einen Zeiger auf eine vom Benutzer erstellten Struktur.|  
|[CPrintInfo::m\_nCurPage](../Topic/CPrintInfo::m_nCurPage.md)|Identifiziert die Seitenzahl, die derzeit gedruckt wird.|  
|[CPrintInfo::m\_nJobNumber](../Topic/CPrintInfo::m_nJobNumber.md)|Gibt die Jobnummer an, die vom Betriebssystem für den aktuellen Druckauftrag zugewiesen ist|  
|[CPrintInfo::m\_nNumPreviewPages](../Topic/CPrintInfo::m_nNumPreviewPages.md)|Identifiziert die Anzahl der Seiten, die im Vorschaufenster angezeigt werden; entweder 1 oder 2.|  
|[CPrintInfo::m\_nOffsetPage](../Topic/CPrintInfo::m_nOffsetPage.md)|Gibt der Offset eines bestimmten DocObjects blättern zuerst in einem kombinierten DocObject\-Druckauftrag an.|  
|[CPrintInfo::m\_pPD](../Topic/CPrintInfo::m_pPD.md)|Enthält einen Zeiger auf `CPrintDialog`\-Objekt, das zum Drucken verwendet wird.|  
|[CPrintInfo::m\_rectDraw](../Topic/CPrintInfo::m_rectDraw.md)|Gibt ein Rechteck, das den aktuellen verwendbaren Seitenbereich definiert.|  
|[CPrintInfo::m\_strPageDesc](../Topic/CPrintInfo::m_strPageDesc.md)|Enthält eine Formatzeichenfolge für Seitenzahlanzeige.|  
  
## Hinweise  
 `CPrintInfo` ist eine Struktur und hat keine Basisklasse.  
  
 Das Framework erstellt ein Objekt aus `CPrintInfo` jedes Mal, wenn der Drucks\- oder Seitenansichtsbefehl aktiviert ist und es zerstört, wenn der Befehl abgeschlossen ist.  
  
 `CPrintInfo` enthält Informationen zu den Druckauftrag insgesamt, wie den Seitenbereich gedruckt werden soll und den aktuellen Status des Druckauftrags, wie der Seite, die aktuell gedruckt wird.  Einige Informationen werden in einem Objekt zugeordneten [CPrintDialog](../../mfc/reference/cprintdialog-class.md) gespeichert; Dieses Objekt enthält die Werte, die vom Benutzer im Dialogfeld Drucken eingegeben werden.  
  
 Ein Objekt `CPrintInfo` wird zwischen dem Framework und die Ansichtsklasse während des Druckvorgangs übergeben und verwendet, um Informationen zwischen den zwei auszutauschen.  Beispielsweise informiert das Framework die Ansichtsklasse, welche Seite des durch das Zuweisen der `m_nCurPage`\-Member von `CPrintInfo` eines Werts zu druckenden Dokuments; die Ansichtsklasse ruft den Wert ab und führt den eigentlichen Drucken der angegebenen Seite aus.  
  
 Ein weiteres Beispiel ist der Fall, in dem die Länge des Dokuments nicht bekannt, bis es gedruckt wird.  In dieser Situation die Ansichtsklassentests für das Ende des Dokuments jedes Mal, wenn eine Seite gedruckt wird.  Wenn das Ende erreicht wird, legt die Ansichtsklasse den `m_bContinuePrinting`\-Member von `CPrintInfo` zu **FALSE** fest; dieses informiert das Framework, um die Drucksschleife zu beenden.  
  
 `CPrintInfo` wird durch die Memberfunktionen von `CView` aufgelistet ist unter "finden auch". Weitere Informationen über die Drucksarchitektur, die von Microsoft Foundation Class\-Bibliothek bereitgestellt wird, finden Sie unter [Rahmenfenster](../../mfc/frame-windows.md) und [Dokument\-\/Ansichtarchitektur](../../mfc/document-view-architecture.md) und die Artikel [Drucken](../../mfc/printing.md) und [Drucken: Mehrseitige Dokumente](../../mfc/multipage-documents.md).  
  
## Vererbungshierarchie  
 `CPrintInfo`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC Sampling DIBLOOK](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)   
 [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)   
 [CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)   
 [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)   
 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)
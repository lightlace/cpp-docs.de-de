---
title: CSplitterWndEx Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0dfacc6bf08aa5b36288a9933ffa9980937f2b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368874"
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx-Klasse



Stellt ein benutzerdefiniertes unterteiltes Fenster dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Standardkonstruktor|  
|`CSplitterWndEx::~CSplitterWndEx`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Wird aufgerufen, durch das Framework ein unterteiltes Fenster gezeichnet werden soll. (Überschreibt [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Hinweise  
 Überschreiben Sie die `OnDrawSplitter` Methode, um die Darstellung der Grafikkomponenten eines unterteilten Fensters anpassen.  
  
 Die `CSplitterWndEx` Klasse dient zusammen mit den [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), und [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) -Methoden, die sind durch einen visuellen Manager implementiert. Um einen visuellen Manager zum Zeichnen einer unterteiltes Fenster in Ihrer Anwendung zu verursachen, ersetzen Sie die Deklarationen von der `CSplitterWnd` -Klasse mit der `CSplitterWndEx` Klasse. Für Anwendungen der Frame-Fenster ist die Fensterklasse Splitter in CMainFrame-Klasse deklariert, die in "MainFrm.h" befindet. Ein Beispiel finden Sie die `OutlookDemo` im Verzeichnis "Samples" Sample.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>  CSplitterWndEx::OnDrawSplitter  
 Wird aufgerufen, durch das Framework ein unterteiltes Fenster gezeichnet werden soll.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext. Wenn dieser Parameter ist `NULL`, das Framework zeichnet des aktiven Fensters.  
  
 [in] `nType`  
 Eines der `CSplitterWnd::ESplitType` Enumerationswerte, der angibt, der Splitter Fensterelement gezeichnet werden soll. Gültige Werte sind `splitBox`, `splitBar`, `splitIntersection` und `splitBorder`.  
  
 [in] `rect`  
 Ein umschließendes Rechteck, das angibt, die Abmessungen und Position der angegebenen Splitter Fensterelement gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../hierarchy-chart.md)   
 [Klassen](mfc-classes.md)   
 [CSplitterWnd-Klasse](csplitterwnd-class.md)   
 [CMFCVisualManager-Klasse](cmfcvisualmanager-class.md)
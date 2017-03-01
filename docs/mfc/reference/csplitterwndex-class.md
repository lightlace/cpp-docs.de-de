---
title: Klasse CSplitterWndEx | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWndEx
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: 24
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 08b26bc2321485181941dbaaa9a903de9a401ef8
ms.lasthandoff: 02/24/2017

---
# <a name="csplitterwndex-class"></a>CSplitterWndEx-Klasse



Stellt ein benutzerdefiniertes unterteiltes Fenster dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|Standardkonstruktor|  
|`CSplitterWndEx::~CSplitterWndEx`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Aufgerufen, um ein unterteiltes Fenster zu zeichnen. (Überschreibt [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>Hinweise  
 Überschreiben Sie die `OnDrawSplitter` Methode, um die Darstellung der Grafikkomponenten eines unterteilten Fensters anpassen.  
  
 Die `CSplitterWndEx` Klasse dient zusammen mit den [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), und [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) Methoden, die durch einen visuellen Manager implementiert werden. Um einen visuellen Manager zum Zeichnen einer unterteiltes Fenster in der Anwendung verursachen, ersetzen Sie die Deklarationen von der `CSplitterWnd` Klasse, wobei die `CSplitterWndEx` Klasse. Frame Fenster handelt wird die Splitter-Fensterklasse in der CMainFrame-Klasse deklariert, die in "MainFrm.h" befindet. Ein Beispiel finden Sie die `OutlookDemo` Beispiel im Beispielverzeichnis.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>Anforderungen  
 **Header:** afxsplitterwndex.h  
  
##  <a name="a-nameondrawsplittera--csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 Aufgerufen, um ein unterteiltes Fenster zu zeichnen.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext. Wenn dieser Parameter `NULL`, das Framework zeichnet das aktive Fenster.  
  
 [in] `nType`  
 Eines der `CSplitterWnd::ESplitType` -Enumerationswerte, der zum Zeichnen der Splitter Window-Element angibt. Gültige Werte sind `splitBox`, `splitBar`, `splitIntersection` und `splitBorder`.  
  
 [in] `rect`  
 Ein umgebendes Rechteck, das die Dimensionen und den Speicherort zum Zeichnen der angegebenen Splitter Window-Element angibt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../hierarchy-chart.md)   
 [Klassen](mfc-classes.md)   
 [CSplitterWnd-Klasse](csplitterwnd-class.md)   
 [CMFCVisualManager-Klasse](cmfcvisualmanager-class.md)

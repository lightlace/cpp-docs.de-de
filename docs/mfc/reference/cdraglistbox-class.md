---
title: CDragListBox Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs: C++
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 424d9db088aa171bdbca868326eb80144a10704b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdraglistbox-class"></a>CDragListBox-Klasse
Zusätzlich zur Bereitstellung der Funktionalität eines Windows-Listenfelds, die `CDragListBox` Klasse kann der Benutzer Listenfeldelemente, beispielsweise Dateinamen, innerhalb des Listenfelds verschieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Erstellt ein `CDragListBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Vom Framework aufgerufen, wenn ein Ziehvorgang gestartet wird.|  
|[CDragListBox::CancelDrag](#canceldrag)|Vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.|  
|[CDragListBox::Dragging](#dragging)|Wird vom Framework aufgerufen, während eines Ziehvorgangs ein.|  
|[CDragListBox::DrawInsert](#drawinsert)|Zeichnet die Einfügemarke im Listenfeld ziehen.|  
|[CDragListBox::Dropped](#dropped)|Wird vom Framework aufgerufen, nachdem das Element gelöscht wurde.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Gibt die Koordinaten des gezogenen Elements zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Listenfelder mit dieser Funktion können Benutzer die Elemente in einer Liste im Verfolgungsinformationen für sie am aussagekräftigsten sind sortieren. Standardmäßig werden im Listenfeld das Element an die neue Position in der Liste verschoben. Allerdings `CDragListBox` Objekte zum Kopieren von Elementen nicht mehr verschoben werden, angepasst werden.  
  
 Das Listenfeld-Steuerelement zugeordneten der `CDragListBox` Klasse dürfen keine der **LBS_SORT** oder **LBS_MULTIPLESELECT** Stil. Eine Beschreibung der Liste im Feld Formatvorlagen, finden Sie unter [Listenfeldstile](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).  
  
 Um ein Listenfeld ziehen Sie im Dialogfeld vorhandene Ihrer Anwendung verwenden zu können, der Dialogfeldvorlage, die mit dem Dialog-Editor ein Listenfeld-Steuerelement hinzugefügt, und weisen Sie eine Membervariable (Kategorie `Control` und Variablentyp `CDragListBox`) entspricht dem Listenfeld in der Dialogfeldvorlage steuern.  
  
 Weitere Informationen zum Zuweisen von Steuerelementen zu Membervariablen finden Sie unter [Tastenkombination für das Definieren von Membervariablen für Dialogfeld-Steuerelemente](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="begindrag"></a>CDragListBox::BeginDrag  
 Wird aufgerufen, durch das Framework beim Eintreten eines Ereignisses ein Ziehvorgangs, z. B. die linke Maustaste drückt beginnen konnte.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten des gezogenen Elements enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ziehen zulässig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie steuern möchten, was geschieht, wenn ein Ziehvorgang begonnen. Die standardmäßige Implementierung erfasst die Maus und bleibt im Ziehmodus, bis der Benutzer klickt auf die linke oder rechte Maustaste gedrückt, oder drücken ESC, die zum Zeitpunkt des Ziehvorgangs abgebrochen wird.  
  
##  <a name="canceldrag"></a>CDragListBox::CancelDrag  
 Vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten des gezogenen Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion für die besondere Verarbeitung für Ihre Listenfeld-Steuerelement.  
  
##  <a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 Erstellt ein `CDragListBox`-Objekt.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>CDragListBox::Dragging  
 Vom Framework aufgerufen, wenn innerhalb einer Listenfeldelement gezogen wird die `CDragListBox` Objekt.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die x- und y enthält Bildschirmkoordinaten des Cursors.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ressourcen-ID des Cursors angezeigt werden. Die folgenden Werte sind möglich:  
  
- `DL_COPYCURSOR`Gibt an, dass das Element kopiert werden sollen.  
  
- `DL_MOVECURSOR`Gibt an, dass das Element verschoben wird.  
  
- `DL_STOPCURSOR`Gibt an, dass die aktuellen Ablageziels nicht zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 Gibt das Standardverhalten `DL_MOVECURSOR`. Überschreiben Sie diese Funktion, wenn Sie zusätzliche Funktionen bereitstellen möchten.  
  
##  <a name="drawinsert"></a>CDragListBox::DrawInsert  
 Wird aufgerufen, durch das Framework die Einfügemarke vor dem Element mit dem angegebenen Index gezeichnet werden soll.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index der Einfügemarke.  
  
### <a name="remarks"></a>Hinweise  
 Ein Wert von – 1 Löscht die Einfügemarke. Überschreiben Sie diese Funktion zum Ändern der Darstellung oder Verhalten von der Einfügemarke.  
  
##  <a name="dropped"></a>CDragListBox::Dropped  
 Vom Framework aufgerufen, wenn ein Element, innerhalb gelöscht wird einer `CDragListBox` Objekt.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 *nSrcIndex*  
 Gibt den nullbasierten Index der gelöschten Zeichenfolge an.  
  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten des Drop-Standorts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten das Listenfeldelement und die Daten an den neuen Speicherort kopiert und löscht dann das ursprüngliche Element. Überschreiben Sie diese Funktion, um das Standardverhalten, z. B. das Aktivieren von Kopien der Listenfeldelemente an anderen Speicherorten in der Liste gezogen wird anpassen.  
  
##  <a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 Aufruf dieser Funktion zum Abrufen des nullbasierten Indexes, der das Listenfeldelement controllerarbeitsverzeichnis `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten eines Punkts innerhalb des Listenfelds enthält.  
  
 *bAutoScroll*  
 Wert ungleich NULL, wenn Scrollen zulässig ist, andernfalls 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des Listenelements Feld ziehen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TSTCON](../../visual-cpp-samples.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)

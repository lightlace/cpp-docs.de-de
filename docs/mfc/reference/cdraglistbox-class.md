---
title: CDragListBox Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- drag list box [C++]
- dragging list items
- CDragListBox class
- Windows [C++], list boxes
- list boxes
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 3010fd9a363aa1ca1c946a6fe967a7ba415649d4
ms.lasthandoff: 02/24/2017

---
# <a name="cdraglistbox-class"></a>CDragListBox-Klasse
Abgesehen von der die Funktionalität eines Windows-Listenfelds die `CDragListBox` -Klasse ermöglicht dem Benutzer Listenfeldelemente, beispielsweise Dateinamen, innerhalb des Listenfelds verschieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Erstellt ein `CDragListBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Vom Framework aufgerufen, wenn ein Ziehvorgang gestartet wird.|  
|[CDragListBox::CancelDrag](#canceldrag)|Wird vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.|  
|[CDragListBox::Dragging](#dragging)|Wird vom Framework aufgerufen, während eines Ziehvorgangs ein.|  
|[CDragListBox::DrawInsert](#drawinsert)|Zeichnet die Einfügemarke im Listenfeld ziehen.|  
|[CDragListBox::Dropped](#dropped)|Wird vom Framework aufgerufen, nachdem das Element gelöscht wurde.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Gibt die Koordinaten des gezogenen Elements zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Listenfelder mit dieser Funktion können Benutzer die Elemente in beliebig besonders nützlich für sie ist in einer Liste zu sortieren. Standardmäßig wird im Listenfeld das Element an die neue Position in der Liste zu verschieben. Allerdings `CDragListBox` Objekte können angepasst werden, um Elemente befinden, zu kopieren.  
  
 Das Listenfeld-Steuerelement zugeordnete der `CDragListBox` Klasse muss keine der **LBS_SORT** oder **LBS_MULTIPLESELECT** Stil. Eine Beschreibung der Liste im Feld Formatvorlagen, finden Sie unter [Listenfeldstile](../../mfc/reference/list-box-styles.md).  
  
 Um ein Listenfeld ziehen Sie im Dialogfeld vorhandene Ihrer Anwendung zu verwenden, ein Listenfeld-Steuerelement hinzufügen, um die Dialogfeldvorlage des Dialog-Editors, und weisen Sie dann eine Membervariable (Kategorie `Control` und Variablentyp `CDragListBox`) für das Listenfeld-Steuerelement in die Dialogfeldvorlage.  
  
 Weitere Informationen zum Zuweisen von Steuerelementen zu Membervariablen finden Sie unter [Verknüpfung für das Definieren von Membervariablen für Dialogfeld-Steuerelemente](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="begindrag"></a>CDragListBox::BeginDrag  
 Aufgerufen durch das Framework beim Eintreten eines Ereignisses ein Ziehvorgangs, z. B. durch Drücken der linken Maustaste beginnen kann.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten des gezogenen Elements enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ziehen zulässig ist, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie steuern, was geschieht, wenn ein Ziehvorgang begonnen werden soll. Die standardmäßige Implementierung die Maus erfasst und in den Dragmodus bleibt, bis der Benutzer auf die linke oder rechte Maustaste oder drücken ESC, woraufhin der Ziehvorgang abgebrochen wird.  
  
##  <a name="canceldrag"></a>CDragListBox::CancelDrag  
 Wird vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten des gezogenen Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um eine spezielle Verarbeitung für Ihre Listenfeld-Steuerelement zu behandeln.  
  
##  <a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 Erstellt ein `CDragListBox`-Objekt.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>CDragListBox::Dragging  
 Vom Framework aufgerufen, wenn ein Listenfeldelement, innerhalb gezogen wird der `CDragListBox` Objekt.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die x- und y enthält die Bildschirmkoordinaten des Cursors.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ressourcen-ID des Cursors angezeigt werden. Die folgenden Werte sind möglich:  
  
- `DL_COPYCURSOR`Gibt an, dass das Element kopiert werden.  
  
- `DL_MOVECURSOR`Gibt an, dass das Element verschoben wird.  
  
- `DL_STOPCURSOR`Gibt an, dass die aktuellen Ablageziels nicht zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 Gibt das Standardverhalten `DL_MOVECURSOR`. Überschreiben Sie diese Funktion, wenn Sie zusätzliche Funktionen bereitstellen möchten.  
  
##  <a name="drawinsert"></a>CDragListBox::DrawInsert  
 Aufgerufen, um den Einfügepunkt vor dem Element mit dem angegebenen Index zu zeichnen.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index der Einfügemarke.  
  
### <a name="remarks"></a>Hinweise  
 Ein Wert von – 1 Löscht den Einfügepunkt. Überschreiben Sie diese Funktion, um die Darstellung oder das Verhalten von der Einfügemarke ändern.  
  
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
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten der Drop-Website enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Standardverhalten des Listenfelds und seine Daten an den neuen Speicherort kopiert und löscht dann das ursprüngliche Element. Überschreiben Sie diese Funktion, um das Standardverhalten, z. B. das Aktivieren von Kopien der Listenfeldelemente an anderen Speicherorten in der Liste gezogen werden anzupassen.  
  
##  <a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 Rufen Sie diese Funktion zum Abrufen des nullbasierten Indexes des Listenelements Feld befindet sich unter `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten eines Punkts innerhalb des Listenfelds enthält.  
  
 *bAutoScroll*  
 Wert ungleich NULL, wenn Bildlauf zulässig ist, andernfalls 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des Listenelements Feld ziehen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel TSTCON](../../visual-cpp-samples.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)


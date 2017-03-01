---
title: Klasse CMFCRibbonSeparator | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonSeparator::GetThisClass
- CMFCRibbonSeparator.CreateObject
- CMFCRibbonSeparator::CreateObject
- CMFCRibbonSeparator
- CreateObject
- CMFCRibbonSeparator.GetThisClass
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator class
- GetThisClass method
- CreateObject method
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 98a58d43b5e6299f26521d873caec06d4581f7b3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator-Klasse
Implementiert das Menüband-Trennzeichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Erstellt ein `CMFCRibbonSeparator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Fügt ein Trennzeichen, die **Befehle** Liste der **anpassen** Dialogfeld. (Überschreibt [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonSeparator::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Eine Copy-Methode, die ein Trennzeichen Variablen aus einem anderen Objekt Elementgruppen.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Gibt die Größe eines Trennzeichens.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Gibt an, ob dies ein Trennzeichen ist.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Gibt an, ob es sich um einen Tabstopp handelt.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Vom System zum Zeichnen von Trennzeichen auf dem Menüband oder die Symbolleiste für den Schnellzugriff aufgerufen.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Vom System auf das Trennzeichen gezeichnet aufgerufen, die **Befehle** Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Menüband-Trennzeichen ist eine vertikale oder horizontale Linie, die logisch trennt die Elemente im Menüband. Eine Trennzeichen kann auf die Menüband-Steuerelement, klicken Sie im Menü des Hauptfensters der Anwendung, der Menüband-Statusleiste und Symbolleiste für den Schnellzugriff gezeichnet werden.  
  
 Um ein Trennzeichen in Ihrer Anwendung verwenden, erstellen Sie das neue Objekt, und fügen Sie es an das Hauptfenster der Anwendung-Menü, wie hier gezeigt:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Rufen Sie [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) menübandbereichen Trennzeichen hinzu. Die Trennzeichen zugeordnet und intern von hinzugefügt werden die `AddSeparator` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbaseribbonelement.h  
  
##  <a name="a-nameaddtolistboxa--cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox  
 Fügt ein Trennzeichen, die **Befehle** Liste der **anpassen** Dialogfeld.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndListBox`  
 Ein Zeiger auf die **Befehle** Liste, in dem das Trennzeichen wird hinzugefügt.  
  
 [in] `bDeep`  
 Ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index der Zeichenfolge im Listenfeld angegebenen `pWndListBox`.  
  
##  <a name="a-namecmfcribbonseparatora--cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator  
 Erstellt ein `CMFCRibbonSeparator`-Objekt.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsHoriz`  
 Wenn `TRUE`, das Trennzeichen ist horizontal; Wenn `FALSE`, das Trennzeichen ist vertikal.  
  
### <a name="remarks"></a>Hinweise  
 Horizontale Trennlinien werden in Menüs verwendet. Symbolleisten werden vertikale Trennzeichen verwendet.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCRibbonSeparator` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp Nr.&19;](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="a-namecopyfroma--cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom  
 Eine Copy-Methode, die ein Trennzeichen Variablen aus einem anderen Objekt Elementgruppen.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Src`  
 Das Menüband Quellelement zum Kopieren aus.  
  
##  <a name="a-namegetregularsizea--cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize  
 Gibt die Größe eines Trennzeichens.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf ein Gerät Inhalt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Trennzeichens für den angegebenen Gerätekontext.  
  
##  <a name="a-nameisseparatora--cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator  
 Gibt an, ob dies ein Trennzeichen ist.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE` für diese Klasse.  
  
##  <a name="a-nameistabstopa--cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop  
 Gibt an, ob es sich um einen Tabstopp handelt.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE` für diese Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüband-Trennzeichen ist ein Tabstopp.  
  
##  <a name="a-nameondrawa--cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCRibbonSeparator::OnDraw  
 Vom System zum Zeichnen von Trennzeichen auf dem Menüband oder die Symbolleiste für den Schnellzugriff aufgerufen.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
##  <a name="a-nameondrawonlista--cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList  
 Vom System auf das Trennzeichen gezeichnet aufgerufen, die **Befehle** Liste.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pDC`|Ein Zeiger zu einem Gerätekontext.|  
|[in] `strText`|Text in der Liste angezeigt.|  
|[in] `nTextOffset`|Der Abstand zwischen dem Text und dem linken Rand des umschließenden Rechtecks.|  
|[in] `rect`|Gibt das umschließende Rechteck.|  
|[in] `bIsSelected`|Ignoriert.|  
|[in] `bHighlighted`|Ignoriert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)


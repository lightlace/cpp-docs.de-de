---
title: CMFCRibbonSeparator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12f4b9019a79b6ff57da6905b6ad9329788b4ec9
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849763"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator-Klasse
Implementiert das Menüband-Trennzeichen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Erstellt ein `CMFCRibbonSeparator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Fügt ein Trennzeichen, das die **Befehle** Liste der **anpassen** Dialogfeld. (Überschreibt [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonSeparator::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Eine Kopiermethode, die ein Trennzeichen des Elements aus einem anderen Objekt Variablen legt diese fest.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Gibt die Größe eines Trennzeichens zurück.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Gibt an, ob dies ein Trennzeichen ist.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Gibt an, ob es sich um einen Tabstopp handelt.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Wird aufgerufen, durch das System an das Trennzeichen auf dem Menüband oder die Symbolleiste für den Schnellzugriff gezeichnet werden soll.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Wird aufgerufen, durch das System zeichnet die Trennlinie der **Befehle** Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Menüband-Trennzeichen ist eine vertikale oder horizontale Linie, die logisch trennt Elemente des Menübands. Eine Trennzeichen kann auf den Steuerelementen des Menübands, klicken Sie im Menü des Hauptfensters der Anwendung, die Status-Menübands und Symbolleiste für den Schnellzugriff gezeichnet werden.  
  
 Um ein Trennzeichen in Ihrer Anwendung verwenden zu können, erstellen Sie das neue Objekt aus, und fügen Sie sie zum Menü "hauptanwendung" wie hier gezeigt:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Rufen Sie [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) menübandbereichen Trennzeichen hinzu. Die Trennzeichen zugeordnet und intern von hinzugefügt werden die `AddSeparator` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox  
 Fügt ein Trennzeichen, das die **Befehle** Liste der **anpassen** Dialogfeld.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndListBox*  
 Ein Zeiger auf die **Befehle** Liste, in dem das Trennzeichen wird hinzugefügt.  
  
 [in] *bDeep*  
 Ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index in die Zeichenfolge in das Listenfeld gemäß *pWndListBox*.  
  
##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator  
 Erstellt ein `CMFCRibbonSeparator`-Objekt.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bIsHoriz*  
 Bei "true", ist das Trennzeichen horizontal; Wenn "FALSE" ist das Trennzeichen vertikal.  
  
### <a name="remarks"></a>Hinweise  
 Horizontale Trennzeichen werden in Anwendungsmenüs verwendet. Vertikale Trennzeichen werden in Symbolleisten verwendet.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonSeparator` Klasse.  
  
 [!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom  
 Eine Kopiermethode, die ein Trennzeichen des Elements aus einem anderen Objekt Variablen legt diese fest.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Src*  
 Das Quellelement des Menübands zum Kopieren aus.  
  
##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize  
 Gibt die Größe eines Trennzeichens zurück.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger auf ein Gerät.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Trennzeichens für den angegebenen Gerätekontext.  
  
##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator  
 Gibt an, ob dies ein Trennzeichen ist.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für diese Klasse immer TRUE.  
  
##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop  
 Gibt an, ob es sich um einen Tabstopp handelt.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für diese Klasse immer FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüband-Trennzeichen ist es sich nicht um einen Tabstopp.  
  
##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw  
 Wird aufgerufen, durch das System an das Trennzeichen auf dem Menüband oder die Symbolleiste für den Schnellzugriff gezeichnet werden soll.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList  
 Wird aufgerufen, durch das System zeichnet die Trennlinie der **Befehle** Liste.  
  
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
|[in] *pDC*|Ein Zeiger zu einem Gerätekontext.|  
|[in] *StrText*|Text in der Liste angezeigt wird.|  
|[in] *nTextOffset*|Der Abstand zwischen dem Text und der linken Seite des umschließenden Rechtecks.|  
|[in] *Rect*|Gibt das umschließende Rechteck.|  
|[in] *bIsSelected*|Ignoriert.|  
|[in] *bHighlighted*|Ignoriert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

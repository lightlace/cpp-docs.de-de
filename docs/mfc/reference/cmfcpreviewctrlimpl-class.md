---
title: CMFCPreviewCtrlImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb1ef84aabed69554ded868bbe9092c3e8b7082f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370411"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl-Klasse
Diese Klasse implementiert ein Fenster, das in einem von der Shell for Rich Preview bereitgestellten Hostfenster platziert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|Destructs ein Vorschau-Control-Objekt.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Erstellt ein Objekt der Preview-Steuerelement.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|Überladen. Wird aufgerufen, von einem Rich Preview-Handler, um das Windows-Fenster zu erstellen.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Wird von einem Rich Preview-Handler aufgerufen, wenn es zerstört das Steuerelement muss.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|Setzt den Eingabefokus auf dieses Steuerelement.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Gibt ein Dokument mit dieser Vorschausteuerelement verbunden.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Weist das Steuerelement zum Neuzeichnen an.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Wird aufgerufen, von der Preview-Handler, der eine Beziehung zwischen der Implementierung des Dokuments und der Preview-Steuerelement zu erstellen.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Legt einen neuen übergeordneten für dieses Steuerelement fest.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Wird aufgerufen, von einem Rich Preview Handler Wenn visuelle Elemente von rich Preview festgelegt werden muss Inhalt.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Legt einen neuen umschließenden Rechtecks für dieses Steuerelement fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Vom Framework aufgerufen, die Vorschau zu rendern.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Hintergrundfarbe des Vorschaufensters.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Die Textfarbe des Vorschaufensters.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Zum Anzeigen von Text im Vorschaufenster verwendete Schriftart.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Ein Zeiger auf ein Dokument, das im Steuerelement zurück, deren Inhalt in der Vorschau angezeigt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
Erstellt ein Objekt der Preview-Steuerelement.

### <a name="syntax"></a>Syntax
CMFCPreviewCtrlImpl();  

## <a name="create"></a> CMFCPreviewCtrlImpl::Create
Überladen. Wird aufgerufen, von einem Rich Preview-Handler, um das Windows-Fenster zu erstellen.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das Hostfenster, die von der Shell for Rich Preview angegeben.  
  
 `prc`  
 Gibt an, die ursprüngliche Größe und Position des Fensters.  
  
 `pContext`  
 Ein Zeiger auf einen Kontext für die Erstellung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Bei erfolgreicher Erstellung andernfalls `FALSE`.  
  
## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy
Wird von einem Rich Preview-Handler aufgerufen, wenn es zerstört das Steuerelement muss.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint  
Vom Framework aufgerufen, die Vorschau zu rendern.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf einen Gerätekontext für das Paint-Ereignisse.  


## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus  
Setzt den Eingabefokus auf dieses Steuerelement.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument
Gibt ein Dokument mit dieser Vorschausteuerelement verbunden.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Dokument, das im Steuerelement zurück, deren Inhalt in der Vorschau angezeigt.

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor  
Hintergrundfarbe des Vorschaufensters.  
  
### <a name="syntax"></a>Syntax  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor
Die Textfarbe des Vorschaufensters.  
  
### <a name="syntax"></a>Syntax  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="m_font"></a> CMFCPreviewCtrlImpl::m_font-Schriftart für Text in einem Vorschaufenster angezeigt.  
  
### <a name="syntax"></a>Syntax  
  
```  
CFont m_font;  
```  
## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument  
Ein Zeiger auf ein Dokument, das im Steuerelement zurück, deren Inhalt in der Vorschau angezeigt.  
  
### <a name="syntax"></a>Syntax  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw  
Weist das Steuerelement zum Neuzeichnen an.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument 
Wird aufgerufen, von der Preview-Handler, der eine Beziehung zwischen der Implementierung des Dokuments und der Preview-Steuerelement zu erstellen.  
  
### <a name="syntax"></a>Syntax  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDocument`  
 Ein Zeiger auf die Implementierung des Dokuments.  

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost  
Legt einen neuen übergeordneten für dieses Steuerelement fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `hWndParent`  
 Ein Handle für das neue übergeordnete Fenster.  

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals  
Wird aufgerufen, von einem Rich Preview Handler Wenn visuelle Elemente von rich Preview festgelegt werden muss Inhalt.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `clrBack`  
 Hintergrundfarbe des Vorschaufensters.  
  
 `clrText`  
 Die Textfarbe des Vorschaufensters.  
  
 `plf`  
 Zum Anzeigen von Text im Vorschaufenster verwendete Schriftart. 

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect  
Legt einen neuen umschließenden Rechtecks für dieses Steuerelement fest.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `prc`  
 Gibt an, die neue Größe und Position des Steuerelements Preview.  
  
 `bRedraw`  
 Gibt an, ob das Steuerelement neu gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel wird ein neues umfassende Rechteck festgelegt, wenn die Hoststeuerelements angepasst wird.  

## <a name="dtor"></a> CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
Destructs ein Vorschau-Control-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  

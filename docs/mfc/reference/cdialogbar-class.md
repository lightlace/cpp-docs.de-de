---
title: CDialogBar-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5477921ff89c8bb0b23245d3848139a7c7c86444
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951555"
---
# <a name="cdialogbar-class"></a>CDialogBar-Klasse
Stellt die Funktionalität eines nicht modalen Windows-Dialogfelds in einer Steuerleiste bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Erstellt ein `CDialogBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Erstellt eine Windows-Dialogleiste und fügt es der `CDialogBar` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Dialogleiste ähnelt ein Dialogfeld, insofern, dass sie Windows-Standardsteuerelemente, denen der Benutzer enthält zwischen TAB-Taste. Eine andere Ähnlichkeit ist das Erstellen einer Dialogfeldvorlage, um die Dialogleiste darzustellen.  
  
 Erstellen und Verwenden einer Dialogleiste gleicht dem Erstellen und Verwenden einer `CFormView` Objekt. Verwenden Sie zuerst die [Dialog-Editor](../../windows/dialog-editor.md) zum Definieren einer Dialogfeldvorlage in dem Format **WS_CHILD** und keine anderen Stil. Die Vorlage darf nicht das Format sein **WS_VISIBLE**. In Ihrem Anwendungscode, rufen Sie den Konstruktor zum Erstellen der `CDialogBar` -Objekt, und rufen Sie dann `Create` zum Erstellen des Zeitfensters für Dialogfeld-weißem Zebrastreifeneffekt und fügen Sie es auf die `CDialogBar` Objekt.  
  
 Weitere Informationen zu `CDialogBar`, finden Sie im Artikel [Dialogleisten](../../mfc/dialog-bars.md) und [technischer Hinweis 31](../../mfc/tn031-control-bars.md), Steuerleisten.  
  
> [!NOTE]
>  In der aktuellen Version ein `CDialogBar` Objekt kann keine Windows Forms-Steuerelemente hosten. Weitere Informationen zu Windows Forms-Steuerelementen in Visual C++ finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar  
 Erstellt ein `CDialogBar`-Objekt.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>  CDialogBar::Create  
 Lädt die im Dialogfeld Ressourcenvorlage gemäß `lpszTemplateName` oder `nIDTemplate`, erstellt die Dialogleiste Fenster, legt den Stil und ordnet sie der `CDialogBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *pParentWnd*  
 Ein Zeiger auf das übergeordnete Element `CWnd` Objekt.  
  
 *lpszTemplateName*  
 Ein Zeiger auf den Namen der `CDialogBar` des Objekts im Dialogfeld Ressourcenvorlage.  
  
 *nStyle*  
 Das Toolbar-Stil. Zusätzliche Toolbar-Stile unterstützt werden:  
  
- **CBRS_TOP** Steuerleiste am oberen Rand des Fensters Frame ist.  
  
- **CBRS_BOTTOM** Steuerleiste am unteren Rand der Frame-Fensters ist.  
  
- **CBRS_NOALIGN** Steuerleiste nicht neu angeordnet, wenn die übergeordnetem Element geändert wird.  
  
- **CBRS_TOOLTIPS** Steuerleiste zeigt QuickInfos an.  
  
- **CBRS_SIZE_DYNAMIC** Steuerleiste ist dynamisch.  
  
- **CBRS_SIZE_FIXED** Steuerleiste ist unveränderlich.  
  
- **CBRS_FLOATING** Steuerleiste unverankert ist.  
  
- **CBRS_FLYBY** Statusleiste zeigt Informationen über die Schaltfläche.  
  
- **CBRS_HIDE_INPLACE** Steuerleiste ist nicht für den Benutzer angezeigt.  
  
 *nID*  
 Die Steuerelement-ID die Dialogleiste.  
  
 *nIDTemplate*  
 Die Ressourcen-ID, der die `CDialogBar` des Objekts im Dialogfeld Vorlage.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Bei Angabe der **CBRS_TOP** oder **CBRS_BOTTOM** Ausrichtungsstil, Breite für die Dialogleiste ist, mit der das Rahmenfenster und seine Höhe ist, mit der durch die angegebene Ressource *nIDTemplate*. Bei Angabe der **CBRS_LEFT** oder **CBRS_RIGHT** Ausrichtungsstil, die Dialogleiste Höhe ist, mit der das Rahmenfenster und seine Breite ist, mit der durch die angegebene Ressource *nIDTemplate*.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel jeder](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)

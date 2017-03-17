---
title: CDialogBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- dialog bars, Windows modeless dialog box
- CDialogBar class
- dialog boxes, modeless
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
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
ms.openlocfilehash: 33dc5f5f4d345745a4b9435e725f411f4387e287
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogbar-class"></a>CDialogBar-Klasse
Stellt die Funktionalität eines nicht modalen Windows-Dialogfelds in einer Steuerleiste bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Erstellt ein `CDialogBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Erstellt eine Windows-Dialogleiste und fügt es der `CDialogBar` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Dialogleiste ähnelt ein Dialogfeld, dass sie Windows-Standardsteuerelemente, denen der Benutzer enthält zwischen die TAB-Taste. Eine andere Ähnlichkeit ist die Erstellung einer Dialogfeldvorlage Dialogleisten darstellen.  
  
 Erstellen und Verwenden einer Dialogleiste ähnelt erstellen und Verwenden einer `CFormView` Objekt. Verwenden Sie zunächst die [Dialog-Editor](../../windows/dialog-editor.md) zum Definieren einer Dialogvorlage im Stil **WS_CHILD** und kein anderer Stil. Die Vorlage muss das Format nicht sein **WS_VISIBLE**. Im Anwendungscode, rufen Sie den Konstruktor zum Erstellen der `CDialogBar` -Objekt, und rufen Sie dann **erstellen** die Dialogleiste Fenster erstellen und Anfügen an die `CDialogBar` Objekt.  
  
 Weitere Informationen zu `CDialogBar`, finden Sie im Artikel [Dialogleisten](../../mfc/dialog-bars.md) und [Technische Hinweis 31](../../mfc/tn031-control-bars.md), Steuerleisten.  
  
> [!NOTE]
>  In der aktuellen Version einer `CDialogBar` Objekt kann keine Windows Forms-Steuerelemente hosten. Weitere Informationen zu Windows Forms-Steuerelemente in Visual C++, finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="cdialogbar"></a>CDialogBar::CDialogBar  
 Erstellt ein `CDialogBar`-Objekt.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>CDialogBar::Create  
 Lädt die Dialogfeld-Ressourcenvorlage angegebenen `lpszTemplateName` oder `nIDTemplate`, erstellt die Dialogleiste Fenster, legt den Stil und ordnet sie der `CDialogBar` Objekt.  
  
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
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Element `CWnd` Objekt.  
  
 `lpszTemplateName`  
 Ein Zeiger auf den Namen der `CDialogBar` des Objekts im Dialogfeld Ressourcenvorlage.  
  
 `nStyle`  
 Der Toolbar-Stil. Zusätzliche Toolbar-Stile, die unterstützt werden:  
  
- `CBRS_TOP`Titelleiste wird am oberen Rand des Frame-Fensters.  
  
- `CBRS_BOTTOM`Steuerleiste ist am unteren Rand des Rahmenfensters.  
  
- `CBRS_NOALIGN`Steuerleiste ist nicht neu angeordnet, die übergeordnetem Element geändert wird.  
  
- `CBRS_TOOLTIPS`Steuerleiste werden QuickInfos angezeigt.  
  
- **CBRS_SIZE_DYNAMIC** Steuerleiste ist dynamisch.  
  
- **CBRS_SIZE_FIXED** Steuerleiste ist fest.  
  
- **CBRS_FLOATING** Steuerleiste ist nicht verankert.  
  
- `CBRS_FLYBY`Statusleiste zeigt Informationen über die Schaltfläche.  
  
- **CBRS_HIDE_INPLACE** Steuerleiste wird dem Benutzer nicht angezeigt.  
  
 `nID`  
 Die Steuerelement-ID der Dialogleisten.  
  
 `nIDTemplate`  
 Die Ressourcen-ID der `CDialogBar` des Objekts im Dialogfeld Vorlage.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Bei Angabe der `CBRS_TOP` oder `CBRS_BOTTOM` Ausrichtungsstil, das Rahmenfenster ist die Dialogleiste Breite und seine Höhe ist, die der angegebenen Ressource `nIDTemplate`. Bei Angabe der `CBRS_LEFT` oder `CBRS_RIGHT` Ausrichtungsstil die Dialogleiste, das Rahmenfenster und beträgt die Breite, die der angegebenen Ressource `nIDTemplate`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCMessageMaps&#13;](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Muster CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFormView-Klasse](../../mfc/reference/cformview-class.md)   
 [CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)


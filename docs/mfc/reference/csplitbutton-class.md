---
title: CSplitButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
dev_langs:
- C++
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbced65aa76206d040ff1c13267fe9b7d3c69eca
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122786"
---
# <a name="csplitbutton-class"></a>CSplitButton-Klasse
Die `CSplitButton` Klasse stellt einen SplitButton-Steuerelement dar. Das Steuerelement mit einer unterteilten Schaltfläche führt ein Standardverhalten aus, wenn ein Benutzer auf den Hauptteil der Schaltfläche klickt, und zeigt ein Dropdownmenü an, wenn ein Benutzer auf den Dropdownpfeil der Schaltfläche klickt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Erstellt ein `CSplitButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Erstellt einen SplitButton-Steuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CSplitButton` Objekt.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Legt die Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Verarbeitet die BCN_DROPDOWN-Benachrichtigungen, die das System sendet, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CSplitButton` abgeleitete Klasse wird von der [CButton](../../mfc/reference/cbutton-class.md) Klasse. Das SplitButton-Steuerelement ist ein Schaltflächensteuerelement, dessen Format BS_SPLITBUTTON ist. Ein benutzerdefiniertes Menü angezeigt, wenn ein Benutzer auf den Dropdown Pfeil klickt. Weitere Informationen finden Sie unter der BS_SPLITBUTTON und BS_DEFSPLITBUTTON Formatvorlagen auf [Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 Die folgende Abbildung zeigt ein Dialogfeld, das einem Pagersteuerelement und eine (1) SplitButton-Steuerelement enthält. (2) Dropdownpfeil bereits geklickt wurde, und (3) Untermenü angezeigt.  
  
 ![Dialogfeld mit einer Trennschaltfläche und einem Pagersteuerelement. ] (../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
 Diese Klasse wird in unterstützt [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
 Zusätzliche Anforderungen für diese Klasse in beschriebenen [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>  CSplitButton::Create  
 Erstellt einen SplitButton-Steuerelement mit der angegebenen Formate und fügt ihn der aktuellen `CSplitButton` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *DwStyle*|Eine bitweise Kombination (OR) von Formaten auf das Steuerelement angewendet werden soll. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/styles-used-by-mfc.md#button-styles).|  
|[in] *Rect*|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] *pParentWnd*|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster des Steuerelements darstellt.|  
|[in] *nID*|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn diese Methode erfolgreich ist; andernfalls "false".  
  
##  <a name="csplitbutton"></a>  CSplitButton::CSplitButton  
 Erstellt ein `CSplitButton`-Objekt. Geben Sie die Parameter des Konstruktors ein Untermenü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das SplitButton-Steuerelement klickt.  
  
```  
CSplitButton();

 
CSplitButton(
    UINT nMenuId,   
    UINT nSubMenuId)  
CSplitButton(CMenu* pMenu)  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *nMenuId*|Die Ressourcen-ID der Menüleiste.|  
|[in] *nSubMenuId*|Die Ressourcen-ID eines Untermenüs.|  
|[in] *pMenu*|Ein Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` Objekt löscht die `CMenu` -Objekt und seine zugehörigen HMENU bei der `CSplitButton` Objekt den Gültigkeitsbereich verlässt.|  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CSplitButton::Create](#create) -Methode erstellen einen SplitButton-Steuerelement und fügen Sie es auf die `CSplitButton` Objekt.  
  
##  <a name="ondropdown"></a>  CSplitButton::OnDropDown  
 Verarbeitet die BCN_DROPDOWN-Benachrichtigungen, die das System sendet, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *pNMHDR*|Zeiger auf eine [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) -Struktur, die Informationen der [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) Benachrichtigung.|  
|[out] *pResult*|(Nicht verwendet, wird kein Wert zurückgegeben.) Der Rückgabewert der [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) Benachrichtigung.|  
  
### <a name="remarks"></a>Hinweise  
 Klickt der Benutzer auf den Dropdown-Pfeil auf einen SplitButton-Steuerelement, System sendet eine Benachrichtigung BCN_DROPDOWN Meldung, die die `OnDropDown` -Methode behandelt. Allerdings die `CSplitButton` Objekt nicht weiter die BCN_DROPDOWN-Benachrichtigung, um das Steuerelement, das SplitButton-Steuerelement enthält. Folglich kann nicht vom enthaltende Steuerelement eine benutzerdefinierte Aktion als Antwort auf die Benachrichtigung unterstützt.  
  
 Verwenden Sie zum Implementieren einer benutzerdefinierten Aktion, die das übergeordnete Steuerelement unterstützt eine [CButton](../../mfc/reference/cbutton-class.md) Objekt mit dem Format BS_SPLITBUTTON anstelle von einer `CSplitButton` Objekt. Implementieren Sie einen Handler für die Benachrichtigung BCN_DROPDOWN in die `CButton` Objekt. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 Um eine benutzerdefinierte Aktion implementieren, um die Trennschaltfläche selbst unterstützt steuern, verwenden [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md). Leiten Sie eine eigene Klasse von der `CSplitButton` Klasse, und nennen Sie sie z. B. CMySplitButton. Fügen Sie die folgenden meldungszuordnung klicken Sie dann auf Ihre Anwendung für die Benachrichtigung BCN_DROPDOWN behandeln:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>  CSplitButton::SetDropDownMenu  
 Legt die Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf die Dropdown-Pfeil, der das aktuelle SplitButton-Steuerelement klickt.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *nMenuId*|Die Ressourcen-ID der Menüleiste.|  
|[in] *nSubMenuId*|Die Ressourcen-ID eines Untermenüs.|  
|[in] *pMenu*|Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` Objekt löscht die `CMenu` -Objekt und seine zugehörigen HMENU bei der `CSplitButton` Objekt den Gültigkeitsbereich verlässt.|  
  
### <a name="remarks"></a>Hinweise  
 Die *nMenuId* Parameter identifiziert eine Menüleiste, also eine horizontale Liste von Menüelementen-Leiste. Die *nSubMenuId* Parameter ist eine nullbasierte Indexnummer, die ein Untermenü wird angegeben, welche die Dropdown-Liste von Menüelementen, die jede Menüleistenelement zugeordnet ist. Eine typische Anwendung hat beispielsweise ein Menü mit den Balken Menüelementen "File", "Bearbeiten" und "Help". "File"-Menüleistenelement verfügt über ein Untermenü, das die Menüelemente enthält "Öffnen", "Schließen" und "Exit". Wenn auf den Dropdownpfeil des unterteilte Schaltfläche des Steuerelements geklickt wird, zeigt das Steuerelement im angegebene Untermenü, nicht in der Menüleiste.  
  
 Die folgende Abbildung zeigt ein Dialogfeld, das einem Pagersteuerelement und eine (1) SplitButton-Steuerelement enthält. (2) Dropdownpfeil bereits geklickt wurde, und (3) Untermenü angezeigt.  
  
 ![Dialogfeld mit einer Trennschaltfläche und einem Pagersteuerelement. ] (../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")  
  
### <a name="example"></a>Beispiel  
 Die erste Anweisung in das folgende Codebeispiel veranschaulicht die [CSplitButton::SetDropDownMenu](#setdropdownmenu) Methode. Wir erstellt das Menü mit den Visual Studio-Ressourcen-Editor, der ID der Menü klicken, wird IDR_MENU1 automatisch benannt. Die *nSubMenuId* -Parameter, der 0 (null) ist, bezieht sich auf das einzige Untermenü die Option der Menüleiste.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CSplitButton-Klasse](../../mfc/reference/csplitbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)

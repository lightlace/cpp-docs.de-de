---
title: Klasse CSplitButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CSplitButton class
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b4c038a177d5c501d4baad8eaa208af0e76ce231
ms.lasthandoff: 02/24/2017

---
# <a name="csplitbutton-class"></a>CSplitButton-Klasse
Die `CSplitButton` -Klasse stellt ein Trennschaltflächen-Steuerelement dar. Das Steuerelement mit einer unterteilten Schaltfläche führt ein Standardverhalten aus, wenn ein Benutzer auf den Hauptteil der Schaltfläche klickt, und zeigt ein Dropdownmenü an, wenn ein Benutzer auf den Dropdownpfeil der Schaltfläche klickt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSplitButton : public CButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::CSplitButton](#csplitbutton)|Erstellt ein `CSplitButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::Create](#create)|Ein Trennschaltflächen-Steuerelement mit der angegebenen Formate erstellt und mit der aktuellen `CSplitButton` Objekt.|  
|[CSplitButton::SetDropDownMenu](#setdropdownmenu)|Legt das Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf den Dropdown-Pfeil der das aktuelle SplitButton-Steuerelement klickt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSplitButton::OnDropDown](#ondropdown)|Behandelt die `BCN_DROPDOWN` Benachrichtigung, die das System sendet, wenn ein Benutzer auf den Dropdown-Pfeil der das aktuelle SplitButton-Steuerelement klickt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CSplitButton` abgeleitete Klasse wird von der [CButton](../../mfc/reference/cbutton-class.md) Klasse. Das SplitButton-Steuerelement ist ein Schaltflächensteuerelement, dessen Stil ist `BS_SPLITBUTTON`. Ein benutzerdefiniertes Menü angezeigt, wenn ein Benutzer auf den Dropdown Pfeil klickt. Weitere Informationen finden Sie unter der `BS_SPLITBUTTON` und `BS_DEFSPLITBUTTON` Stile in [Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb775951).  
  
 Die folgende Abbildung zeigt ein Dialogfeld mit einem Pagersteuerelement und ein (1) SplitButton-Steuerelement. (2) Dropdownpfeil bereits geklickt wurde, und klicken Sie im Untermenü (3) wird angezeigt.  
  
 ![Dialogfeld mit einer Trennschaltfläche und einem Pagersteuerelement. ] (../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CSplitButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
 Diese Klasse wird in unterstützt [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)] und höher.  
  
 Zusätzliche Anforderungen für diese Klasse finden Sie im [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).  
  
##  <a name="create"></a>CSplitButton::Create  
 Ein Trennschaltflächen-Steuerelement mit der angegebenen Formate erstellt und mit der aktuellen `CSplitButton` Objekt.  
  
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
|[in] `dwStyle`|Eine bitweise Kombination (OR) der Formate auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/button-styles.md).|  
|[in] `rect`|Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements enthält.|  
|[in] `pParentWnd`|Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|  
|[in] `nID`|Die ID des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
##  <a name="csplitbutton"></a>CSplitButton::CSplitButton  
 Erstellt ein `CSplitButton`-Objekt. Geben Sie die Parameter des Konstruktors ein Untermenü, das angezeigt wird, wenn ein Benutzer auf den Dropdown-Pfeil der das SplitButton-Steuerelement klickt.  
  
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
|[in] `nMenuId`|Die Ressourcen-ID der Menüleiste.|  
|[in] `nSubMenuId`|Die Ressourcen-ID eines Untermenüs.|  
|[in] `pMenu`|Ein Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` -Objekt löscht die `CMenu` -Objekt und die zugehörigen `HMENU` bei der `CSplitButton` -Objekt den Gültigkeitsbereich verlässt.|  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CSplitButton::Create](#create) Methode, um ein Trennschaltflächen-Steuerelement zu erstellen, und fügen Sie es auf die `CSplitButton` Objekt.  
  
##  <a name="ondropdown"></a>CSplitButton::OnDropDown  
 Behandelt die `BCN_DROPDOWN` Benachrichtigung, die das System sendet, wenn ein Benutzer auf den Dropdown-Pfeil der das aktuelle SplitButton-Steuerelement klickt.  
  
```  
afx_msg void OnDropDown(
    NMHDR* pNMHDR,   
    LRESULT* pResult);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pNMHDR`|Zeiger auf eine [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) -Struktur, die Informationen der [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) Benachrichtigung.|  
|[out] `pResult`|(Nicht verwendet, wird kein Wert zurückgegeben.) Der Rückgabewert der [BCN_DROPDOWN](http://msdn.microsoft.com/library/windows/desktop/bb775983) Benachrichtigung.|  
  
### <a name="remarks"></a>Hinweise  
 Klickt der Benutzer auf den Dropdown-Pfeil auf ein Trennschaltflächen-Steuerelement, sendet das System eine `BCN_DROPDOWN` Benachrichtigung angezeigt, die die `OnDropDown` -Methode behandelt. Allerdings die `CSplitButton` Objekt nicht mehr die `BCN_DROPDOWN` Benachrichtigung an das Steuerelement, das SplitButton-Steuerelement enthält. Daher kann nicht das übergeordnete Steuerelement eine benutzerdefinierte Aktion als Antwort auf die Benachrichtigung unterstützen.  
  
 Verwenden Sie zum Implementieren einer benutzerdefinierten Aktion, die das übergeordnete Steuerelement unterstützt eine [CButton](../../mfc/reference/cbutton-class.md) Objekt mit dem Format `BS_SPLITBUTTON` statt einer `CSplitButton` Objekt. Implementieren Sie einen Handler für das `BCN_DROPDOWN` Benachrichtigung in der `CButton` Objekt. Weitere Informationen finden Sie unter [Schaltflächenstile](../../mfc/reference/button-styles.md).  
  
 Verwenden Sie zum Implementieren einer benutzerdefinierten Aktion, dass die Trennschaltfläche selbst unterstützt das Steuerelement [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md). Leiten Sie eine eigene Klasse von der `CSplitButton` Klasse, und nennen Sie sie z. B. CMySplitButton. Klicken Sie dann die folgende Nachricht Zuordnung Ihrer Anwendung behandeln hinzufügen die `BCN_DROPDOWN` Benachrichtigung:  
  
```  
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)  
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)  
END_MESSAGE_MAP()  
```  
  
##  <a name="setdropdownmenu"></a>CSplitButton::SetDropDownMenu  
 Legt das Dropdown-Menü, das angezeigt wird, wenn ein Benutzer auf den Dropdown-Pfeil der das aktuelle SplitButton-Steuerelement klickt.  
  
```  
void SetDropDownMenu(
    UINT nMenuId,   
    UINT nSubMenuId);  
  
void SetDropDownMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nMenuId`|Die Ressourcen-ID der Menüleiste.|  
|[in] `nSubMenuId`|Die Ressourcen-ID eines Untermenüs.|  
|[in] `pMenu`|Zeiger auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt, das ein Untermenü angibt. Die `CSplitButton` -Objekt löscht die `CMenu` -Objekt und die zugehörigen `HMENU` bei der `CSplitButton` -Objekt den Gültigkeitsbereich verlässt.|  
  
### <a name="remarks"></a>Hinweise  
 Die `nMenuId` Parameter identifiziert eine Menüleiste, eine horizontale Liste der Menüelemente angezeigt wird. Der `nSubMenuId` -Parameter ist eine nullbasierte Indexnummer, die ein Untermenü identifiziert, die die Dropdown-Liste der Menüelemente, die jede Menüleistenelement zugeordnet ist. Beispielsweise weist eine normale Anwendung ein Menü mit der Leiste Menüelemente "Datei", "Bearbeiten" und "Hilfe". Der "Datei" Menüleistenelement verfügt über ein Untermenü, das die Menüelemente enthält "Öffnen", "Schließen" und "Exit". Wenn der Dropdown-Pfeil des Split-Schaltflächen-Steuerelements geklickt wird, zeigt das Steuerelement im angegebene Untermenü nicht in der Menüleiste.  
  
 Die folgende Abbildung zeigt ein Dialogfeld mit einem Pagersteuerelement und ein (1) SplitButton-Steuerelement. (2) Dropdownpfeil bereits geklickt wurde, und klicken Sie im Untermenü (3) wird angezeigt.  
  
 ![Dialogfeld mit einer Trennschaltfläche und einem Pagersteuerelement. ] (../../mfc/reference/media/splitbutton_pager.png "Splitbutton_pager")  
  
### <a name="example"></a>Beispiel  
 Die erste Anweisung in das folgende Codebeispiel veranschaulicht die [CSplitButton::SetDropDownMenu](#setdropdownmenu) Methode. Wir Ressourcen-Editor, die automatisch die Leiste-ID genannt, klicken Sie im Menü mit Visual Studio erstellten `IDR_MENU1`. Der `nSubMenuId` -Parameter, der NULL ist, bezieht sich auf das einzige Untermenü der Menüleiste.  
  
 [!code-cpp[NVC_MFC_CSplitButton_s&#2;1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CSplitButton-Klasse](../../mfc/reference/csplitbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)


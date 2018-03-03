---
title: CMFCRibbonCustomizePropertyPage Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ad58cb0b062e25a52742eec5491489d3744a9ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage-Klasse
Implementiert eine benutzerdefinierte Seite für die **anpassen** Dialogfeld in Menüband-basierten Anwendungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|Erstellt ein `CMFCRibbonCustomizePropertyPage`-Objekt.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Fügt eine benutzerdefinierte Kategorie, um die **Befehle** Kombinationsfeld.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Vom System aufgerufen wird, wenn ein Benutzer klickt **OK** auf die **anpassen** (Dialogfeld).|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie benutzerdefinierte Befehle hinzufügen möchten die **anpassen** (Dialogfeld), müssen Sie die Nachricht AFX_WM_ON_RIBBON_CUSTOMIZE behandeln. Instanziieren Sie in der Message-Handler einer `CMFCRibbonCustomizePropertyPage` Objekt auf dem Stapel. Erstellen Sie eine Liste von benutzerdefinierten Befehlen, und rufen dann `AddCustomCategory` hinzuzufügende neue Seite, um die **anpassen** (Dialogfeld).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonCustomizePropertyPage` Objekt und eine benutzerdefinierte Kategorie hinzufügen.  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncustomizedialog.h  
  
##  <a name="addcustomcategory"></a>CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 Fügt eine benutzerdefinierte Kategorie, um die **Befehle** Kombinationsfeld.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `lpszName`|Gibt den Namen der benutzerdefinierten Softwarekategorie an.|  
|[in] `lstIDS`|Enthält die Menübandbefehls-IDs in der benutzerdefinierten Kategorie angezeigt werden.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt eine Kategorie mit dem Namen `lpszName` auf die **Befehle** Kombinationsfeld. Wenn der Benutzer die Kategorie auswählt, wird die Befehle in angegebenen `lstIDS` in der Befehlsliste angezeigt.  
  
##  <a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Erstellt ein `CMFCRibbonCustomizePropertyPage`-Objekt.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRibbonBar`  
 Ein Zeiger auf ein Menübandsteuerelement für die die Optionen zum Anpassen.  
  
##  <a name="onok"></a>CMFCRibbonCustomizePropertyPage::OnOK  
 Vom System klickt ein Benutzer Calleld **OK** auf die **anpassen** (Dialogfeld).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gilt, die im ausgewählten Optionen der **anpassen** Dialogfeld auf der Symbolleiste für den Schnellzugriff.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

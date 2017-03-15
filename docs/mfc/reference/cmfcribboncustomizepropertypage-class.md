---
title: Klasse CMFCRibbonCustomizePropertyPage | Microsoft-Dokumentation
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
- CMFCRibbonCustomizePropertyPage::CreateObject
- CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage.GetThisClass
- CMFCRibbonCustomizePropertyPage.CreateObject
- ~CMFCRibbonCustomizePropertyPage
- CreateObject
- CMFCRibbonCustomizePropertyPage.~CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage::GetThisClass
dev_langs:
- C++
helpviewer_keywords:
- ~CMFCRibbonCustomizePropertyPage destructor
- CMFCRibbonCustomizePropertyPage class, destructor
- GetThisClass method
- CreateObject method
- CMFCRibbonCustomizePropertyPage class
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 83323142441de13140383152a32122bf1644003f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage-Klasse
Implementiert eine benutzerdefinierte Seite für die **anpassen** Dialogfeld im Menüband-basierte Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|Fügt eine benutzerdefinierte Kategorie der **Befehle** Kombinationsfeld.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|Vom System aufgerufen wird, wenn ein Benutzer klickt **OK** auf der **anpassen** Dialogfeld.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie benutzerdefinierte Befehle hinzufügen möchten die **anpassen** Dialogfeld müssen Sie die AFX_WM_ON_RIBBON_CUSTOMIZE-Nachricht verarbeiten. Instanziieren Sie in der Message-Handler ein `CMFCRibbonCustomizePropertyPage` Objekt im Stapel. Erstellen Sie eine Liste mit benutzerdefinierten Befehlen, und rufen Sie dann `AddCustomCategory` Hinzufügen der neue Seite den **anpassen** Dialogfeld.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCRibbonCustomizePropertyPage` Objekt und eine benutzerdefinierte Kategorie hinzufügen.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#22;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncustomizedialog.h  
  
##  <a name="a-nameaddcustomcategorya--cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a>CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 Fügt eine benutzerdefinierte Kategorie der **Befehle** Kombinationsfeld.  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `lpszName`|Gibt den Namen der benutzerdefinierten Kategorie an.|  
|[in] `lstIDS`|Enthält die Multifunktionsleiste Befehls-IDs in der benutzerdefinierten Kategorie angezeigt werden.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt eine Kategorie mit dem Namen `lpszName` an der **Befehle** Kombinationsfeld. Bei der Auswahl der Kategorie, die Befehle in angegebenen `lstIDS` in der Befehlsliste angezeigt.  
  
##  <a name="a-namecmfcribboncustomizepropertypagea--cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 Erstellt ein `CMFCRibbonCustomizePropertyPage`-Objekt.  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRibbonBar`  
 Ein Zeiger auf ein Menübandsteuerelement, für das die Optionen zum Anpassen.  
  
##  <a name="a-nameonoka--cmfcribboncustomizepropertypageonok"></a><a name="onok"></a>CMFCRibbonCustomizePropertyPage::OnOK  
 Vom System klickt ein Benutzer Calleld **OK** auf der **anpassen** Dialogfeld.  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung übernimmt die Optionen der **anpassen** Dialogfeld Symbolleiste für den Schnellzugriff.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)


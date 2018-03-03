---
title: CMFCPropertyGridFontProperty Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 505f48bcfb867ae8444d8dbbee360bb04e23d8e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty-Klasse
Die `CMFCPropertyGridFileProperty` Klasse unterstützt die Listenelement-Steuerelement eine Eigenschaft, die ein Dialogfeld des zur Schriftartauswahl öffnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Erstellt ein `CMFCPropertyGridFontProperty`-Objekt.|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts. (Überschreibt [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Ruft die Schriftfarbe, die der Benutzer über das Schriftartdialogfeld auswählt.|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Ruft die Schriftart, die der Benutzer über das Schriftartdialogfeld auswählt.|  
|`CMFCPropertyGridFontProperty::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyGridFontProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist. (Überschreibt [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 Erstellt ein `CMFCPropertyGridFontProperty`-Objekt.  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strName`  
 Den Namen der Eigenschaft.  
  
 [in] `lf`  
 Eine logische Schriftart-Struktur, die die Attribute der Schriftart angibt.  
  
 [in] `dwFontDialogFlags`  
 Formatvorlagen, die im Dialogfeld "Schriftart" angewendet werden, die angezeigt wird, wenn Sie die Eigenschaft Wert Dropdown-Schaltfläche klicken. Der Standardwert ist die bitweise Kombination (OR) von CF_EFFECTS und CF_SCREENFONTS. Weitere Informationen finden Sie unter der `Flags` Parameter von der [CHOOSEFONT Struktur](http://msdn.microsoft.com/library/windows/desktop/ms646832).  
  
 [in] `lpszDescr`  
 Beschreibung der Font-Eigenschaft. Der Standardwert ist `NULL`.  
  
 [in] `dwData`  
 Anwendungsspezifische Daten, z. B. eine ganze Zahl oder ein Zeiger auf andere Daten, die der Eigenschaft zugeordnet ist. Der Standardwert ist 0.  
  
 [in] `color`  
 Die Farbe der Schriftart. Der Standardwert ist die Standardfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCPropertyGridFontProperty` Objekt eine Schriftarteigenschaft im Eigenschaftenraster-Steuerelement eine Schriftart darstellt.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie ein Objekt des erstellen die `CMFCPropertyGridFontProperty` Klasse. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 Ruft die Schriftfarbe, die der Benutzer über das Schriftartdialogfeld auswählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Farbwert, der die Farbe der ausgewählten Schriftart darstellt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 Ruft die Schriftart, die der Benutzer über das Schriftartdialogfeld auswählt.  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur, die die ausgewählte Schriftart beschreibt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

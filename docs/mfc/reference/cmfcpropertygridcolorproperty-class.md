---
title: CMFCPropertyGridColorProperty Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de336692a821ba374996fac9ee7d282d2990bd08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertygridcolorproperty-class"></a>CMFCPropertyGridColorProperty-Klasse
Die `CMFCPropertyGridColorProperty`-Klasse unterstützt ein Eigenschaftslisten-Steuerelement, über das ein Farbauswahl-Dialogfeld geöffnet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Erstellt ein `CMFCPropertyGridColorProperty`-Objekt.|  
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Ermöglicht die *automatische* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der standard Schaltfläche "automatisch" ist mit der Bezeichnung **automatische**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Ermöglicht die *andere* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der Standard ist mit der Schaltfläche "Sonstige" Bezeichnung **Weitere Farben**.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts. (Überschreibt [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Ruft die aktuelle Farbe der Eigenschaft ab.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist. (Überschreibt [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Wird vom Framework aufgerufen, um die Liste der Eigenschaftenwerte anzuzeigen. (Überschreibt [cmfcpropertygridproperty:: Ondrawvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Wird vom Framework aufgerufen, wenn der Benutzer dabei ist, einen Eigenschaftenwert zu bearbeiten. (Überschreibt [cmfcpropertygridproperty:: onEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Wird vom Framework aufgerufen, wenn der Wert einer änderbaren Eigenschaft geändert wurde. (Überschreibt [cmfcpropertygridproperty:: Onupdatevalue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Legt eine neue Farbe für die Eigenschaft fest.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Gibt die Anzahl der Spalten in der aktuellen Farbe des Eigenschaftenrasters an.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPropertyGridColorProperty` -Klasse unterstützt eine Farbeigenschaft, die zu einem Eigenschaftenlisten-Steuerelement hinzugefügt werden kann. Weitere Informationen finden Sie unter der [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt `CMFCPropertyGridColorProperty`- Klasse erstellt und mithilfe der verschiedenen Methoden der `CMFCPropertyGridColorProperty`-Klasse konfiguriert wird. Der Code erläutert, wie die Schaltflächen „automatisch“ und „sonstige“ aktiviert werden und wie die Farbe und die Spaltenanzahl festgelegt wird. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridcolorproperty"></a>  CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty  
 Erstellt ein `CMFCPropertyGridColorProperty`-Objekt.  
  
```  
CMFCPropertyGridColorProperty(
    const CString& strName,  
    const COLORREF& color,  
    CPalette* pPalette = NULL,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strName`  
 Den Namen der Eigenschaft.  
  
 [in] `color`  
 Den Farbwert der Eigenschaft.  
  
 [in] `pPalette`  
 Ein Zeiger auf eine Palette von Farben. Der Standardwert ist `NULL`.  
  
 [in] `lpszDescr`  
 Die Beschreibung der Eigenschaft. Der Standardwert ist `NULL`.  
  
 [in] `dwData`  
 Anwendungsspezifische Daten, z. B. eine ganze Zahl oder ein Zeiger auf andere Daten, die der Eigenschaft zugeordnet ist. Der Standardwert ist 0.  
  
##  <a name="enableautomaticbutton"></a>  CMFCPropertyGridColorProperty::EnableAutomaticButton  
 Ermöglicht die *automatische* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der standard Schaltfläche "automatisch" ist mit der Bezeichnung **automatische**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Der Bezeichnungstext für die Schaltfläche "automatisch".  
  
 [in] `colorAutomatic`  
 Die RGB-Farbwert der automatisch (Standard)-Farbe.  
  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie die Schaltfläche "Automatische"; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableotherbutton"></a>  CMFCPropertyGridColorProperty::EnableOtherButton  
 Ermöglicht die *andere* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der Standard ist mit der Schaltfläche "Sonstige" Bezeichnung **Weitere Farben**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Der Bezeichnungstext, der die Schaltfläche "Sonstige" werden soll.  
  
 [in] `bAltColorDlg`  
 `TRUE` zum Anzeigen der `CMFCColorDialog` Dialogfeld; `FALSE` die standard-Farbauswahl-Dialogfeld angezeigt. Der Standardwert ist `TRUE`.  
  
 [in] `bEnable`  
 `TRUE` auf die Schaltfläche "Sonstige" angezeigt. andernfalls `FALSE`.  Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolor"></a>  CMFCPropertyGridColorProperty::GetColor  
 Ruft die aktuelle Farbe der Eigenschaft ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolor"></a>  CMFCPropertyGridColorProperty::SetColor  
 Legt eine neue Farbe für die Eigenschaft fest.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolumnsnumber"></a>  CMFCPropertyGridColorProperty::SetColumnsNumber  
 Gibt die Anzahl der Spalten in der aktuellen Farbe des Eigenschaftenrasters an.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumnsNumber`  
 Die gewünschte Anzahl der Spalten in der Farbe des Eigenschaftenrasters.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt den Wert für die `m_nColumnsNumber` Datenmember geschützt.  
  
##  <a name="setoriginalvalue"></a>  CMFCPropertyGridColorProperty::SetOriginalValue  
 Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `varValue`  
 Ein Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [cmfcpropertygridproperty:: Resetoriginalvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) -Methode zum Zurücksetzen des ursprünglichen Wert einer bearbeiteten Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

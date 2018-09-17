---
title: CMFCPropertyGridColorProperty-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 7b1023ff59af0f64d5205447e6e7b17ead1f5186
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705834"
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
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Ermöglicht die *automatische* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Die standardmäßige automatische Schaltfläche ist mit der Bezeichnung **automatische**.)|  
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Ermöglicht die *andere* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der Standard andere Schaltfläche ist mit der Bezeichnung **Weitere Farben**.)|  
|`CMFCPropertyGridColorProperty::FormatProperty`|Formatiert die Textdarstellung eines Eigenschaftswerts. (Überschreibt [cmfcpropertygridproperty:: Formatproperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|  
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Ruft die aktuelle Farbe der Eigenschaft ab.|  
|`CMFCPropertyGridColorProperty::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyGridColorProperty::OnClickButton`|Wird vom Framework aufgerufen, wenn der Benutzer auf eine Schaltfläche klickt, die in einer Eigenschaft enthalten ist. (Überschreibt [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
|`CMFCPropertyGridColorProperty::OnDrawValue`|Wird vom Framework aufgerufen, um die Liste der Eigenschaftenwerte anzuzeigen. (Überschreibt [cmfcpropertygridproperty:: Ondrawvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|  
|`CMFCPropertyGridColorProperty::OnEdit`|Wird vom Framework aufgerufen, wenn der Benutzer dabei ist, einen Eigenschaftenwert zu bearbeiten. (Überschreibt [cmfcpropertygridproperty:: onEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|  
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Wird vom Framework aufgerufen, wenn der Wert einer änderbaren Eigenschaft geändert wurde. (Überschreibt [cmfcpropertygridproperty:: Onupdatevalue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|  
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Legt eine neue Farbe für die Eigenschaft fest.|  
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Gibt die Anzahl der Spalten in der aktuellen Farbe des Eigenschaftenrasters an.|  
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPropertyGridColorProperty` -Klasse unterstützt eine Farbeigenschaft, die zu einem Eigenschaftenlisten-Steuerelement hinzugefügt werden kann. Weitere Informationen finden Sie unter den [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt `CMFCPropertyGridColorProperty`- Klasse erstellt und mithilfe der verschiedenen Methoden der `CMFCPropertyGridColorProperty`-Klasse konfiguriert wird. Der Code erläutert, wie die Schaltflächen „automatisch“ und „sonstige“ aktiviert werden und wie die Farbe und die Spaltenanzahl festgelegt wird. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
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
*strName*<br/>
[in] Der Name der Eigenschaft.  
  
*Farbe*<br/>
[in] Der Farbwert der Eigenschaft.  
  
*pPalette*<br/>
[in] Zeiger auf eine Palette von Farben. Der Standardwert ist NULL.  
  
*lpszDescr*<br/>
[in] Beschreibung der Eigenschaft. Der Standardwert ist NULL.  
  
*dwData*<br/>
[in] Anwendungsspezifische Daten, z. B. eine ganze Zahl oder ein Zeiger auf andere Daten, die der Eigenschaft zugeordnet ist. Der Standardwert ist 0.  
  
##  <a name="enableautomaticbutton"></a>  CMFCPropertyGridColorProperty::EnableAutomaticButton  
 Ermöglicht die *automatische* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Die standardmäßige automatische Schaltfläche ist mit der Bezeichnung **automatische**.)  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszLabel*<br/>
[in] Der Bezeichnungstext, der die automatische Schaltfläche werden soll.  
  
*colorAutomatic*<br/>
[in] Der RGB-Farbwert der Farbe automatisch (Standard).  
  
*bAktivieren*<br/>
[in] True, um die automatische Schaltfläche zu aktivieren. andernfalls "false". Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableotherbutton"></a>  CMFCPropertyGridColorProperty::EnableOtherButton  
 Ermöglicht die *andere* Schaltfläche auf das Dialogfeld zur Farbauswahl. (Der Standard andere Schaltfläche ist mit der Bezeichnung **Weitere Farben**.)  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg = TRUE,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszLabel*<br/>
[in] Der Bezeichnungstext der anderen Schaltfläche.  
  
*bAltColorDlg*<br/>
[in] "True" Anzeige der `CMFCColorDialog` Dialogfeld FALSE, um das Dialogfeld für die Auswahl des Standardfarbe anzuzeigen. Der Standardwert ist "true".  
  
*bAktivieren*<br/>
[in] TRUE, wenn die anderen Schaltfläche angezeigt werden soll; andernfalls "false".  Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolor"></a>  CMFCPropertyGridColorProperty::GetColor  
 Ruft die aktuelle Farbe der Eigenschaft ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Farbwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolor"></a>  CMFCPropertyGridColorProperty::SetColor  
 Legt eine neue Farbe für die Eigenschaft fest.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
*Farbe*<br/>
[in] Ein RGB-Farbwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolumnsnumber"></a>  CMFCPropertyGridColorProperty::SetColumnsNumber  
 Gibt die Anzahl der Spalten in der aktuellen Farbe des Eigenschaftenrasters an.  
  
```  
void SetColumnsNumber(int nColumnsNumber);
```  
  
### <a name="parameters"></a>Parameter  
*nColumnsNumber*<br/>
[in] Die bevorzugte Anzahl von Spalten in der Farbe des Eigenschaftenrasters.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt den Wert fest. die `m_nColumnsNumber` Datenmember geschützt.  
  
##  <a name="setoriginalvalue"></a>  CMFCPropertyGridColorProperty::SetOriginalValue  
 Legt den ursprünglichen Wert einer bearbeitbaren Eigenschaft fest.  
  
```  
virtual void SetOriginalValue(const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parameter  
*varValue*<br/>
[in] Ein-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [cmfcpropertygridproperty:: Resetoriginalvalue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) Methode, um den ursprünglichen Wert einer bearbeiteten Eigenschaft zurückzusetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

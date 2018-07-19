---
title: CMFCPropertyGridFileProperty-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dd70e67769d35bf50e52b7be4b2c8848c089cb0
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37851599"
---
# <a name="cmfcpropertygridfileproperty-class"></a>CMFCPropertyGridFileProperty-Klasse
Die `CMFCPropertyGridFileProperty` Klasse unterstützt, einem Eigenschaftenlisten-Steuerelement ein Element, das ein Dialogfeld zur Dateiauswahl geöffnet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Erstellt ein `CMFCPropertyGridFileProperty`-Objekt.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(Überschreibt [cmfcpropertygridproperty:: Onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
 Erstellt ein `CMFCPropertyGridFileProperty`-Objekt.  
  
```  
CMFCPropertyGridFileProperty(
    const CString& strName,  
    BOOL bOpenFileDialog,  
    const CString& strFileName,  
    LPCTSTR lpszDefExt=NULL,  
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter=NULL,  
    LPCTSTR lpszDescr=NULL,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *StrName*  
 Der Eigenschaftenname.  
  
 [in] *bOpenFileDialog*  
 "True" Öffnen Sie eine **Datei öffnen** Dialogfeld "False" zum Öffnen einer **Datei speichern** Dialogfeld.  
  
 [in] *StrFileName*  
 Der ursprüngliche Dateiname.  
  
 [in] *LpszDefExt*  
 Eine Zeichenfolge mit einer oder mehreren Dateierweiterungen. Der Standardwert ist NULL.  
  
 [in] *DwFlags*  
 Dialogfeldflags. Der Standardwert ist eine bitweise Kombination (OR) von OFN_HIDEREADONLY und OFN_OVERWRITEPROMPT.  
  
 [in] *LpszFilter*  
 Eine Zeichenfolge mit einer oder mehreren Dateinfiltern. Der Standardwert ist NULL.  
  
 [in] *LpszDescr*  
 Die Beschreibung des Eigenschaftenelements. Der Standardwert ist NULL.  
  
 [in] *DwData*  
 Anwendungsspezifische Daten, die dem Eigenschaftenelement zugeordnet sind. Zum Beispiel eine 32-Bit-Ganzzahl oder ein Zeiger auf andere Daten. Der Standardwert ist 0.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Eine vollständige Liste der verfügbaren Flags finden Sie unter [OPENFILENAME-Struktur](https://msdn.microsoft.com/library/ms646839.aspx).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit dem Konstruktor der `CMFCPropertyGridFileProperty` Klasse erstellt wird. In diesem Beispiel ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

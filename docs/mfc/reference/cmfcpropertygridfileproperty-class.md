---
title: CMFCPropertyGridFileProperty-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 5022063fe7eb8242f01684438e2fdeeeedc80616
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302896"
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

*strName*<br/>
[in] Der Eigenschaftenname.

*bOpenFileDialog*<br/>
[in] "True" Öffnen Sie eine **Datei öffnen** Dialogfeld "False" zum Öffnen einer **Datei speichern** Dialogfeld.

*strFileName*<br/>
[in] Der ursprüngliche Dateiname.

*lpszDefExt*<br/>
[in] Eine Zeichenfolge, der eine oder mehrere Dateierweiterungen. Der Standardwert ist NULL.

*dwFlags*<br/>
[in] Dialogfeldflags. Der Standardwert ist eine bitweise Kombination (OR) von OFN_HIDEREADONLY und OFN_OVERWRITEPROMPT.

*lpszFilter*<br/>
[in] Eine Zeichenfolge mit einem oder mehreren dateinfiltern. Der Standardwert ist NULL.

*lpszDescr*<br/>
[in] Die Beschreibung des Eigenschaftenelements. Der Standardwert ist NULL.

*dwData*<br/>
[in] Anwendungsspezifische Daten, die dem Eigenschaftenelement zugeordnet ist. Zum Beispiel eine 32-Bit-Ganzzahl oder ein Zeiger auf andere Daten. Der Standardwert ist 0.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Eine vollständige Liste der verfügbaren Flags finden Sie unter [OPENFILENAME-Struktur](/windows/desktop/api/commdlg/ns-commdlg-tagofna).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit dem Konstruktor der `CMFCPropertyGridFileProperty` Klasse erstellt wird. In diesem Beispiel ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

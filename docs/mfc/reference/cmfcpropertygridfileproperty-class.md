---
title: Cmfcpropertygridfileproperty-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
ms.openlocfilehash: 4b64d18a67ea499c202b81481684227200846483
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821282"
---
# <a name="cmfcpropertygridfileproperty-class"></a>Cmfcpropertygridfileproperty-Klasse

Die `CMFCPropertyGridFileProperty` -Klasse unterstützt ein Eigenschaften Listen-Steuerelement, das ein Dialogfeld zur Dateiauswahl öffnet.

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
|`CMFCPropertyGridFileProperty::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|`CMFCPropertyGridFileProperty::OnClickButton`|(Überschreibt [cmfcpropertygridproperty:: onclickbutton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

### <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertygridctrl. h

##  <a name="cmfcpropertygridfileproperty"></a>Cmfcpropertygridfileproperty:: cmfcpropertygridfileproperty

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
in Der Eigenschaftsname.

*bOpenFileDialog*<br/>
in TRUE, um das Dialogfeld **Datei öffnen** zu öffnen. FALSE, um das Dialogfeld **Datei speichern** zu öffnen.

*strFileName*<br/>
in Der ursprüngliche Dateiname.

*lpszDefExt*<br/>
in Eine Zeichenfolge mit einer oder mehreren Dateinamen Erweiterungen. Der Standardwert ist NULL.

*dwFlags*<br/>
in Dialog Feld-Flags. Der Standardwert ist eine bitweise Kombination (OR) von OFN_HIDEREADONLY und OFN_OVERWRITEPROMPT.

*lpszFilter*<br/>
in Eine Zeichenfolge mit einem oder mehreren Dateifiltern. Der Standardwert ist NULL.

*lpszDescr*<br/>
in Die Beschreibung des Eigenschafts Elements. Der Standardwert ist NULL.

*dwData*<br/>
in Anwendungsspezifische Daten, die dem Eigenschaften Element zugeordnet sind. Zum Beispiel eine 32-Bit-Ganzzahl oder ein Zeiger auf andere Daten. Der Standardwert ist 0.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Eine vollständige Liste der verfügbaren Flags finden Sie unter [OpenFileName-Struktur](/windows/win32/api/commdlg/ns-commdlg-openfilenamew).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein Objekt mit dem Konstruktor der `CMFCPropertyGridFileProperty` Klasse erstellt wird. Dieses Beispiel ist Teil des [Visual Studio-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCPropertyGridCtrl-Klasse](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)

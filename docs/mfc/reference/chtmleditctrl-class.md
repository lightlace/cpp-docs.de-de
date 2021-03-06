---
title: CHtmlEditCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: 6f5c465a8ec9c8f54af5545e66fb849a08d241af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389410"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl-Klasse

Stellt die Funktionalität des WebBrowser-ActiveX-Steuerelements in einem MFC-Fenster bereit.

## <a name="syntax"></a>Syntax

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Erstellt ein `CHtmlEditCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHtmlEditCtrl::Create](#create)|Erstellt ein WebBrowser ActiveX-Steuerelement, und fügt es der `CHtmlEditCtrl` Objekt. Diese Funktion setzt automatisch das WebBrowser ActiveX-Steuerelement in den Bearbeitungsmodus.|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Ruft die [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) Schnittstelle für das Dokument derzeit geladen, im WebBrowser-Steuerelement enthalten.|
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Ruft die URL ab, der ein Standarddokument in der enthaltenen WebBrowser-Steuerelement geladen.|

## <a name="remarks"></a>Hinweise

Die gehostete WebBrowser, die Steuerelement automatisch angezeigt wird, in Bearbeitungsmodus befindet, nachdem dieser erstellt wurde.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxhtml.h

##  <a name="chtmleditctrl"></a>  CHtmlEditCtrl::CHtmlEditCtrl

Erstellt ein `CHtmlEditCtrl`-Objekt.

```
CHtmlEditCtrl();
```

##  <a name="create"></a>  CHtmlEditCtrl::Create

Erstellt ein WebBrowser ActiveX-Steuerelement, und fügt es der `CHtmlEditCtrl` Objekt. Der WebBrowser ActiveX Steuerelement automatisch zu einem Standarddokument navigiert und dann befindet sich im Bearbeitungsmodus befindet, von dieser Funktion.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

*lpszWindowName*<br/>
Dieser Parameter wird nicht verwendet.

*dwStyle*<br/>
Dieser Parameter wird nicht verwendet.

*rect*<br/>
Gibt an, die Größe und Position des Steuerelements.

*pParentWnd*<br/>
Gibt die übergeordnete Fenster des Steuerelements an. Es darf nicht NULL sein.

*nID*<br/>
Gibt an, der ID des Steuerelements

*pContext*<br/>
Dieser Parameter wird nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getdhtmldocument"></a>  CHtmlEditCtrl::GetDHtmlDocument

Ruft die [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) Schnittstelle für das Dokument derzeit geladen, im enthaltenen WebBrowser-Steuerelement

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parameter

*ppDocument*<br/>
Die Dokumentschnittstelle.

##  <a name="getstartdocument"></a>  CHtmlEditCtrl::GetStartDocument

Ruft die URL ab, der ein Standarddokument in der enthaltenen WebBrowser-Steuerelement geladen.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

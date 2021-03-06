---
title: CHtmlEditDoc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: c2a00b2501647f6101fed8ed1d4cd23dad7ab209
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346187"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc-Klasse

Mit [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), stellt die Funktionalität der WebBrowser-Bearbeitungsplattform im Rahmen der MFC Dokument-/ Ansichtarchitektur bereit.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Erstellt ein `CHtmlEditDoc`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|Ruft die `CHtmlEditView` Objekt angefügt, um in diesem Dokument.|
|[CHtmlEditDoc::IsModified](#ismodified)|Gibt zurück, ob die zugeordnete Ansicht WebBrowser-Steuerelement, ein Dokument enthält, die vom Benutzer geändert wurde.|
|[CHtmlEditDoc::OpenURL](#openurl)|Öffnet eine URL an.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>Anforderungen

**Header:** afxhtml.h

##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc

Erstellt ein `CHtmlEditDoc`-Objekt.

```
CHtmlEditDoc();
```

##  <a name="getview"></a>  CHtmlEditDoc::GetView

Ruft die [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) Objekt angefügt, um in diesem Dokument.

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf des Dokuments des `CHtmlEditView` Objekt.

##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified

Gibt zurück, ob die zugeordnete Ansicht WebBrowser-Steuerelement, ein Dokument enthält, die vom Benutzer geändert wurde.

```
virtual BOOL IsModified();
```

##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL

Öffnet eine URL an.

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parameter

*lpszURL*<br/>
Die URL zu öffnen.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

## <a name="see-also"></a>Siehe auch

[HTMLEdit-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

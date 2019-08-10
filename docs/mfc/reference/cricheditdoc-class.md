---
title: CRichEditDoc-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRichEditDoc
- AFXRICH/CRichEditDoc
- AFXRICH/CRichEditDoc::CreateClientItem
- AFXRICH/CRichEditDoc::GetStreamFormat
- AFXRICH/CRichEditDoc::GetView
- AFXRICH/CRichEditDoc::m_bRTF
helpviewer_keywords:
- CRichEditDoc [MFC], CreateClientItem
- CRichEditDoc [MFC], GetStreamFormat
- CRichEditDoc [MFC], GetView
- CRichEditDoc [MFC], m_bRTF
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
ms.openlocfilehash: d296185fe2ea2216f4abe17b191f71b6fa36e1f9
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916706"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc-Klasse

Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [cricheditcntetem](../../mfc/reference/cricheditcntritem-class.md)stellt die Funktionalität des Rich-Edit-Steuer Elements im Kontext der MFC-Dokument Ansichts Architektur bereit.

## <a name="syntax"></a>Syntax

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|Wird aufgerufen, um die Bereinigung des Dokuments auszuführen.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Gibt an, ob Stream-Eingaben und-Ausgaben Formatierungsinformationen enthalten sollen.|
|[CRichEditDoc::GetView](#getview)|Ruft das asssatenated [CRichEditView](../../mfc/reference/cricheditview-class.md) -Objekt ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|Gibt an, ob die Stream-e/a Formatierungen enthalten soll.|

## <a name="remarks"></a>Hinweise

Ein "Rich Edit-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann. Dem Text kann eine Zeichen-und Absatz Formatierung zugewiesen werden, die eingebettete OLE-Objekte enthalten kann. Rich Edit-Steuerelemente stellen eine Programmierschnittstelle zum Formatieren von Text bereit. Allerdings muss eine Anwendung alle Benutzeroberflächen Komponenten implementieren, die für das verfügbar machen von Formatierungs Vorgängen für den Benutzer erforderlich sind.

`CRichEditView`behält den Text und das Formatierungs Merkmal von Text bei. `CRichEditDoc`verwaltet die Liste der Client Elemente in der Ansicht. `CRichEditCntrItem`bietet Container seitigen Zugriff auf die OLE-Client Elemente.

Dieses allgemeine Windows-Steuerelement (und daher die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) -Klasse und verwandte Klassen) ist nur für Programme verfügbar, die unter Windows 95/98 und Windows NT, Version 3,51 und höher, ausgeführt werden.

Ein Beispiel für die Verwendung eines Rich-Edit-Dokuments in einer MFC-Anwendung finden Sie in der Beispielanwendung [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Anforderungen

**Header:** afxrich. h

##  <a name="createclientitem"></a>CRichEditDoc:: kreateclientitem

Rufen Sie diese Funktion auf, `CRichEditCntrItem` um ein-Objekt zu erstellen und dieses Dokument hinzuzufügen.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parameter

*preo*<br/>
Ein Zeiger auf eine [reobject](/windows/desktop/api/richole/ns-richole-reobject) -Struktur, die ein OLE-Element beschreibt. Das neue `CRichEditCntrItem` -Objekt wird um dieses OLE-Element erstellt. Wenn *preo* den Wert NULL hat, ist das neue Client Element leer.

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein neues [cricheditcnytem](../../mfc/reference/cricheditcntritem-class.md) -Objekt, das diesem Dokument hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion führt keine OLE-Initialisierung aus.

Weitere Informationen finden Sie in der [reobject](/windows/desktop/api/richole/ns-richole-reobject) -Struktur in der Windows SDK.

##  <a name="getstreamformat"></a>CRichEditDoc:: getstreamformat

Mit dieser Funktion können Sie das Textformat für das Streaming der Inhalte des Rich-Edit-Vorgangs bestimmen.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Rückgabewert

Eines der folgenden Flags:

- SF_TEXT gibt an, dass das Rich Edit-Steuerelement keine Formatierungsinformationen beibehält.

- SF_RTF gibt an, dass das Rich Edit-Steuerelement Formatierungsinformationen beibehält.

### <a name="remarks"></a>Hinweise

Der Rückgabewert basiert auf dem [m_bRTF](#m_brtf) -Datenmember. Diese Funktion gibt SF_RTF zurück `m_bRTF` , wenn den Wert true hat, andernfalls SF_TEXT.

##  <a name="getview"></a>CRichEditDoc:: GetView

Mit dieser Funktion greifen Sie auf das [CRichEditView](../../mfc/reference/cricheditview-class.md) -Objekt zu `CRichEditDoc` , das diesem Objekt zugeordnet ist.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf das `CRichEditView` -Objekt, das dem Dokument zugeordnet ist.

### <a name="remarks"></a>Hinweise

Die Text-und Formatierungsinformationen sind im `CRichEditView` -Objekt enthalten. Das `CRichEditDoc` -Objekt verwaltet die OLE-Elemente für die Serialisierung. Es darf nur ein `CRichEditView` für jedes `CRichEditDoc`vorhanden sein.

##  <a name="m_brtf"></a>CRichEditDoc:: m_bRTF

TRUE gibt an, dass [CRichEditCtrl:: StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) und [CRichEditCtrl:: StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) Absatz-und Zeichen Formatierungsmerkmale speichern sollen.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WordPad](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument-Klasse](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl-Klasse](../../mfc/reference/cricheditctrl-class.md)

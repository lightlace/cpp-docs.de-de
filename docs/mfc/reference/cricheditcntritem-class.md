---
title: Cricheditcnytem-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
helpviewer_keywords:
- CRichEditCntrItem [MFC], CRichEditCntrItem
- CRichEditCntrItem [MFC], SyncToRichEditObject
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
ms.openlocfilehash: 8e242504c8ab0f59f6dec0602d4a5352a2d84867
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502729"
---
# <a name="cricheditcntritem-class"></a>Cricheditcnytem-Klasse

Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)stellt die Funktionalität des Rich-Edit-Steuer Elements im Kontext der MFC-Dokument Ansichts Architektur bereit.

## <a name="syntax"></a>Syntax

```
class CRichEditCntrItem : public COleClientItem
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Erstellt ein `CRichEditCntrItem`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Aktiviert das Element als einen anderen Typ.|

## <a name="remarks"></a>Hinweise

Ein "Rich Edit-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann. Dem Text kann eine Zeichen-und Absatz Formatierung zugewiesen werden, die eingebettete OLE-Objekte enthalten kann. Rich Edit-Steuerelemente stellen eine Programmierschnittstelle zum Formatieren von Text bereit. Allerdings muss eine Anwendung alle Benutzeroberflächen Komponenten implementieren, die für das verfügbar machen von Formatierungs Vorgängen für den Benutzer erforderlich sind.

`CRichEditView`behält den Text und das Formatierungs Merkmal von Text bei. `CRichEditDoc`verwaltet die Liste der OLE-Client Elemente in der Ansicht. `CRichEditCntrItem`bietet Container seitigen Zugriff auf das OLE-Client Element.

Dieses allgemeine Windows-Steuerelement (und daher die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) -Klasse und verwandte Klassen) ist nur für Programme verfügbar, die unter Windows 95/98 und Windows NT, Version 3,51 und höher, ausgeführt werden.

Ein Beispiel für die Verwendung von Rich-Edit-Container Elementen in einer MFC-Anwendung finden Sie in der Beispielanwendung [WordPad](../../overview/visual-cpp-samples.md) .

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleClientItem](../../mfc/reference/coleclientitem-class.md)

`CRichEditCntrItem`

## <a name="requirements"></a>Anforderungen

**Header:** afxrich. h

##  <a name="cricheditcntritem"></a>Cricheditcntiertem:: cricheditcntrierer

Rufen Sie diese Funktion auf, `CRichEditCntrItem` um ein-Objekt zu erstellen und es dem Container Dokument hinzuzufügen.

```
CRichEditCntrItem(
    REOBJECT* preo = NULL,
    CRichEditDoc* pContainer = NULL);
```

### <a name="parameters"></a>Parameter

*preo*<br/>
Ein Zeiger auf eine [reobject](/windows/win32/api/richole/ns-richole-reobject) -Struktur, die ein OLE-Element beschreibt. Das neue `CRichEditCntrItem` -Objekt wird um dieses OLE-Element erstellt. Wenn *preo* den Wert NULL hat, ist das Client Element leer.

*pContainer*<br/>
Zeiger auf das Container Dokument, das dieses Element enthält. Wenn *pContainer* NULL ist, müssen Sie [COleDocument:: AddItem](../../mfc/reference/coledocument-class.md#additem) explizit aufzurufen, um dieses Client Element einem Dokument hinzuzufügen.

### <a name="remarks"></a>Hinweise

Diese Funktion führt keine OLE-Initialisierung aus.

Weitere Informationen finden Sie in der [reobject](/windows/win32/api/richole/ns-richole-reobject) -Struktur in der Windows SDK.

##  <a name="synctoricheditobject"></a>Cricheditcntertem:: synctoricheditobject

Diese Funktion wird aufgerufen, um den Geräte Aspekt ( [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect)) dieses `CRichEditCntrltem` mit dem von *REO*angegebenen zu synchronisieren.

```
void SyncToRichEditObject(REOBJECT& reo);
```

### <a name="parameters"></a>Parameter

*REO*<br/>
Verweis auf eine [reobject](/windows/win32/api/richole/ns-richole-reobject) -Struktur, die ein OLE-Element beschreibt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [DVASPECT](/windows/win32/api/wtypes/ne-wtypes-dvaspect) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WordPad](../../overview/visual-cpp-samples.md)<br/>
[COleClientItem-Klasse](../../mfc/reference/coleclientitem-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc-Klasse](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)

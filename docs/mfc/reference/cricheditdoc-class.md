---
title: CRichEditDoc Class
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
ms.openlocfilehash: 4cc3af7649d30a153b67cd8269e595c11018833f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769787"
---
# <a name="cricheditdoc-class"></a>CRichEditDoc Class

Mit [CRichEditView](../../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), stellt die Funktionalität des rich-Edit-Steuerelements im Kontext der MFC Dokument-/ Ansichtarchitektur bereit.

## <a name="syntax"></a>Syntax

```
class CRichEditDoc : public COleServerDoc
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditDoc::CreateClientItem](#createclientitem)|Wird aufgerufen, um die Bereinigung des Dokuments auszuführen.|
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Gibt an, ob Stream Eingabe und Ausgabe Formatierungsinformationen enthalten soll.|
|[CRichEditDoc::GetView](#getview)|Ruft den Zeilenindex [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CRichEditDoc::m_bRTF](#m_brtf)|Gibt an, ob die e/a-Stream Formatieren von aufzunehmen.|

## <a name="remarks"></a>Hinweise

Als "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text Zeichen- und absatzformatierung zugewiesen werden kann, und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die textformatierung an. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich, um Formatierungsvorgängen für den Benutzer verfügbar zu machen implementieren.

`CRichEditView` verwaltet den Text und Formatierung Merkmal des Texts. `CRichEditDoc` verwaltet die Liste der Clientelemente in der Ansicht sind. `CRichEditCntrItem` ermöglicht den Zugriff von Container-Seite für die OLE-Client-Elemente.

Diese allgemeinen Windows-Steuerelements (und somit die [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) und verwandten Klassen) ist nur für Programme, die unter Versionen des Windows 95/98 und Windows NT 3.51 und höher.

Ein Beispiel für eine rich-Edit-Dokument in einer MFC-Anwendung verwenden, finden Sie unter den [WORDPAD](../../overview/visual-cpp-samples.md) beispielanwendung.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

[COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)

[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

`CRichEditDoc`

## <a name="requirements"></a>Anforderungen

**Header:** afxrich.h

##  <a name="createclientitem"></a>  CRichEditDoc::CreateClientItem

Mit dieser Funktion wird zum Erstellen einer `CRichEditCntrItem` Objekt aus, und fügen Sie es in diesem Dokument hinzu.

```
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;
```

### <a name="parameters"></a>Parameter

*preo*<br/>
Zeiger auf ein [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Struktur, die ein OLE-Element beschreibt. Die neue `CRichEditCntrItem` Objekt wird erstellt, um diese OLE-Element. Wenn *Preo* NULL ist, das neue Clientelement ist leer.

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein neues [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) Objekt, das in diesem Dokument hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Diese Funktion führt keine OLE-Initialisierung aus.

Weitere Informationen finden Sie unter den [REOBJECT](/windows/desktop/api/richole/ns-richole-_reobject) Struktur im Windows SDK.

##  <a name="getstreamformat"></a>  CRichEditDoc::GetStreamFormat

Rufen Sie diese Funktion aus, um zu bestimmen, die Text-Format für den Inhalt des rich-Edit-streaming.

```
int GetStreamFormat() const;
```

### <a name="return-value"></a>Rückgabewert

Eine der folgenden Flags:

- SF_TEXT gibt an, dass die Rich--Steuerelement Edit werden Informationen über die Formatierung nicht verwaltet werden.

- SF_RTF gibt an, dass die Rich--Steuerelement Edit werden die Formatierungsinformationen verwaltet.

### <a name="remarks"></a>Hinweise

Der zurückgegebene Wert basiert auf der [M_bRTF](#m_brtf) -Datenmember. Diese Funktion gibt SF_RTF zurück, wenn `m_bRTF` "true" ist, andernfalls SF_TEXT.

##  <a name="getview"></a>  CRichEditDoc::GetView

Rufen Sie diese Funktion den Zugriff auf die [CRichEditView](../../mfc/reference/cricheditview-class.md) Objekt zugeordneten `CRichEditDoc` Objekt.

```
virtual CRichEditView* GetView() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die `CRichEditView` Objekt, mit dem Dokument verknüpft ist.

### <a name="remarks"></a>Hinweise

Der Text und Formatieren der Informationen sind in enthalten die `CRichEditView` Objekt. Die `CRichEditDoc` -Objekt verwaltet die OLE-Elemente für die Serialisierung. Nur ein SqlEndAltersStep vorhanden sein `CRichEditView` für jede `CRichEditDoc`.

##  <a name="m_brtf"></a>  M_brtf

Wenn "true" gibt an, dass [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) und [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) Absatz und der zeichenformatierung Eigenschaften speichern soll.

```
BOOL m_bRTF;
```

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel WORDPAD](../../overview/visual-cpp-samples.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)<br/>
[CRichEditCntrItem-Klasse](../../mfc/reference/cricheditcntritem-class.md)<br/>
[COleDocument-Klasse](../../mfc/reference/coledocument-class.md)<br/>
[CRichEditCtrl-Klasse](../../mfc/reference/cricheditctrl-class.md)

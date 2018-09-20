---
title: COleCmdUI-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9fe0365440823a394bee44d84bcecd6ed0b70c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439093"
---
# <a name="colecmdui-class"></a>COleCmdUI-Klasse

Implementiert eine Methode, die es MFC ermöglicht, den Zustand von Benutzeroberflächenobjekten zu aktualisieren, die in Bezug zu den `IOleCommandTarget`-gesteuerten Funktionen der Anwendung stehen.

## <a name="syntax"></a>Syntax

```
class COleCmdUI : public CCmdUI
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleCmdUI::COleCmdUI](#colecmdui)|Erstellt ein `COleCmdUI`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleCmdUI::Enable](#enable)|Legt fest oder löscht der Befehl-Flag aktivieren.|
|[COleCmdUI::SetCheck](#setcheck)|Legt den Status einer Umschaltfläche ein-und Befehl.|
|[COleCmdUI::SetText](#settext)|Gibt eine Textzeichenfolge Name oder Status für einen Befehl zurück.|

## <a name="remarks"></a>Hinweise

In einer Anwendung ist, die nicht für DocObjects, aktiviert, wenn der Benutzeransichten ein Menü in der MFC-Anwendung verarbeitet, wähle ich UPDATE_COMMAND_UI. Jede Benachrichtigung erhält eine [CCmdUI](../../mfc/reference/ccmdui-class.md) -Objekt, das bearbeitet werden kann, um den Zustand eines bestimmten Befehls wiederzugeben. Wenn Sie jedoch Ihre Anwendung für DocObjects aktiviert ist, MFC UPDATE_OLE_COMMAND_UI Benachrichtigungen verarbeitet und weist `COleCmdUI` Objekte.

`COleCmdUI` ermöglicht DocObject um Befehle zu empfangen, die in der zugehörigen Containers-Benutzeroberfläche (z. B. FileNew, Open, Print und So weiter) stammen, und einen Container aus, um Befehle zu empfangen, die auf das Objekt in der Benutzeroberfläche stammen. Obwohl `IDispatch` verwendet werden, um die gleichen Befehle senden `IOleCommandTarget` bietet eine einfachere Möglichkeit zum Abfragen und ausgeführt werden, da es auf einen Standardsatz von Befehlen in der Regel ohne Argumente beruht ein, und keine Typinformationen beteiligt ist. `COleCmdUI` kann verwendet werden, zu aktivieren, aktualisieren und Festlegen anderer Eigenschaften des DocObject Befehlen der Benutzeroberfläche. Wenn Sie den Befehl aufrufen möchten, rufen Sie [COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd).

Weitere Informationen zu DocObjects, finden Sie unter [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) und [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CCmdUI](../../mfc/reference/ccmdui-class.md)

`COleCmdUI`

## <a name="requirements"></a>Anforderungen

**Header:** afxdocobj.h

##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI

Erstellt eine `COleCmdUI` Objekt verknüpft ist, mit einem bestimmten Benutzeroberflächen-Befehl.

```
COleCmdUI(
    OLECMD* rgCmds,
    ULONG cCmds,
    const GUID* m_pGroup);
```

### <a name="parameters"></a>Parameter

*rgCmds*<br/>
Eine Liste der unterstützten Befehle, die die angegebene GUID zugeordnet. Die `OLECMD` Struktur ordnet Befehle Befehlsflags.

*cCmds*<br/>
Die Anzahl der Befehle in *RgCmds*.

*pGroup*<br/>
Ein Zeiger auf eine GUID, die eine Reihe von Befehlen identifiziert.

### <a name="remarks"></a>Hinweise

Die `COleCmdUI` Objekt stellt eine programmgesteuerte Schnittstelle zum Aktualisieren von Benutzeroberflächenobjekten DocObject wie z. B. Steuerleiste-Schaltflächen oder Menüelemente. Die Objekte der Benutzeroberfläche können werden aktiviert, deaktiviert, überprüft und/oder gelöscht wird, über die `COleCmdUI` Objekt.

##  <a name="enable"></a>  COleCmdUI::Enable

Mit dieser Funktion wird zum Festlegen der Kennzeichnung des Befehls von der `COleCmdUI` Objekt OLECOMDF_ENABLED, die der Schnittstelle mitteilt, der Befehl ist verfügbar und aktiviert, oder deaktivieren Sie die Kennzeichnung des Befehls.

```
virtual void Enable(BOOL bOn);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
Gibt an, ob mit der Befehl verknüpft die `COleCmdUI` Objekt aktiviert oder deaktiviert werden soll. Nonzero können den Befehl. 0 deaktiviert den Befehl.

##  <a name="setcheck"></a>  COleCmdUI::SetCheck

Mit dieser Funktion können Sie den Status einer Umschaltfläche ein-und Befehl.

```
virtual void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parameter

*nPrüfen*<br/>
Ein Wert, der den Status einer Umschaltfläche ein-und Befehl. Gültige Werte:

|Wert|Beschreibung|
|-----------|-----------------|
|**1**|Legt fest, der Befehl auf.|
|**2**|Der Befehl festgelegt einem unbestimmten Zustand; der Zustand kann nicht bestimmt werden, da das Attribut mit diesem Befehl sowohl auf und Deaktivieren der Zustände in der entsprechenden Auswahl wird.|
|ein anderer Wert|Der Befehl auf off festgelegt.|

##  <a name="settext"></a>  COleCmdUI::SetText

Rufen Sie diese Funktion, um eine Textzeichenfolge Name oder Status für einen Befehl zurück.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Ein Zeiger auf den Text, mit dem Befehl verwendet werden.

## <a name="see-also"></a>Siehe auch

[CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)




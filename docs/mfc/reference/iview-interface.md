---
title: IView-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84ed9bfb8b0c8b5ab30af07d8f0448109161df51
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077763"
---
# <a name="iview-interface"></a>IView-Schnittstelle

Implementiert einige Methoden, die [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen an einem verwalteten Steuerelement verwendet.

## <a name="syntax"></a>Syntax

```
interface class IView
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|Wird von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert ist.|
|[IView:: OnInitialUpdate](#oninitialupdate)|Vom Framework aufgerufen, nachdem die Ansicht zuerst auf das Dokument angefügt ist, aber vor die Ansicht angezeigt wird.|
|[IView::OnUpdate](#onupdate)|Von MFC aufgerufen, nachdem das Dokument von der Ansicht geändert wurde; Diese Funktion kann es sich um die Ansicht seine Anzeige Änderungen entsprechend aktualisiert.|

## <a name="remarks"></a>Hinweise

`IView` implementiert einige Methoden, die `CWinFormsView` verwendet, um eine allgemeine Ansicht Benachrichtigungen zu einem gehosteten verwalteten Steuerelement weitergeleitet. Hierbei handelt es sich [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) und [OnActivateView](#onactivateview).

`IView` ist vergleichbar mit [CView](../../mfc/reference/cview-class.md), jedoch nur mit verwalteten Ansichten und Steuerelementen verwendet wird.

Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [verwenden ein Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Anforderungen

Header: afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)

## <a name="onactivateview"></a> IView::OnActivateView

Wird von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert ist.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>Parameter

*Aktivieren*<br/>
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.

## <a name="oninitialupdate"></a> IView:: OnInitialUpdate

Vom Framework aufgerufen, nachdem die Ansicht zuerst auf das Dokument angefügt ist, aber vor die Ansicht angezeigt wird.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate

Von MFC aufgerufen, nachdem das Dokument von der Ansicht geändert wurde.
```
void OnUpdate();
```

## <a name="remarks"></a>Hinweise

Diese Funktion kann es sich um die Ansicht seine Anzeige Änderungen entsprechend aktualisiert.

## <a name="see-also"></a>Siehe auch

[CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)

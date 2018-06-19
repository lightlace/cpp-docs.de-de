---
title: IView-Schnittstelle | Microsoft Docs
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
ms.openlocfilehash: a06243af3de7a2f4b32aa9a9ae492dfe3b2d3b64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370958"
---
# <a name="iview-interface"></a>IView-Schnittstelle
Implementiert mehrere Möglichkeiten, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen, die an eine verwaltete Steuerelement verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Wird von MFC aufgerufen, wenn eine Sicht aktiviert oder deaktiviert ist.|  
|[IView:: OnInitialUpdate](#oninitialupdate)|Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.|  
|[IView::OnUpdate](#onupdate)|Von MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde; mit dieser Funktion können die Ansicht, um die Aktualisierung der Anzeige, um Änderungen widerzuspiegeln.|  
  
## <a name="remarks"></a>Hinweise  
 `IView` implementiert mehrere Möglichkeiten, `CWinFormsView` verwendet, um allgemeine Benachrichtigungen anzeigen, die zu einem verwalteten gehosteten Steuerelement weiterzuleiten. Hierbei handelt es sich [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) und [OnActivateView](#onactivateview).  
  
 `IView` ähnelt dem [CView](../../mfc/reference/cview-class.md), aber nur mit verwalteten Ansichten und Steuerelemente verwendet wird.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Anforderungen  
 Header: afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  

## <a name="onactivateview"></a> IView::OnActivateView  
Wird von MFC aufgerufen, wenn eine Sicht aktiviert oder deaktiviert ist.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Parameter
`activate`  
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  

## <a name="oninitialupdate"></a> IView:: OnInitialUpdate
Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate 
Wird von MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde.  
```
void OnUpdate();
```
## <a name="remarks"></a>Hinweise  
Mit dieser Funktion können die Ansicht, um die Aktualisierung der Anzeige, um Änderungen widerzuspiegeln.

## <a name="see-also"></a>Siehe auch  
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)

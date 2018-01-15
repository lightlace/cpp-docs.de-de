---
title: IView-Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
dev_langs: C++
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4266d8f5ec564dac67d7167c6c9bab4768a0276
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 `IView`implementiert mehrere Möglichkeiten, `CWinFormsView` verwendet, um allgemeine Benachrichtigungen anzeigen, die zu einem verwalteten gehosteten Steuerelement weiterzuleiten. Hierbei handelt es sich [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) und [OnActivateView](#onactivateview).  
  
 `IView`ähnelt dem [CView](../../mfc/reference/cview-class.md), aber nur mit verwalteten Ansichten und Steuerelemente verwendet wird.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Anforderungen  
 Header: afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  

## <a name="onactivateview"></a>IView::OnActivateView  
Wird von MFC aufgerufen, wenn eine Sicht aktiviert oder deaktiviert ist.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Parameter
`activate`  
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  

## <a name="oninitialupdate"></a>IView:: OnInitialUpdate
Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber bevor die Ansicht anfänglich angezeigt wird.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
Wird von MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde.  
```
void OnUpdate();
```
## <a name="remarks"></a>Hinweise  
Mit dieser Funktion können die Ansicht, um die Aktualisierung der Anzeige, um Änderungen widerzuspiegeln.

## <a name="see-also"></a>Siehe auch  
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)

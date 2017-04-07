---
title: IView-Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IView
- No header/IView
- No header/IView::OnActivateView
- No header/IView::OnInitialUpdate
- No header/IView::OnUpdate
dev_langs:
- C++
helpviewer_keywords:
- views [MFC]
- IView class
- views, classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9a8b5f2d9d123aa3032cb30ecdbdd1cd380b32f8
ms.lasthandoff: 02/24/2017

---
# <a name="iview-interface"></a>IView--Schnittstelle
Implementiert mehrere Möglichkeiten, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) zum Senden von Benachrichtigungen anzeigen an einem verwalteten Steuerelement verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
interface class IView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IView::OnActivateView](#onactivateview)|Von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert wird.|  
|[IView:: OnInitialUpdate](#oninitialupdate)|Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber vor dem Beginn der Ansicht angezeigt wird.|  
|[IView::OnUpdate](#onupdate)|Von MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde. mit dieser Funktion können die Ansicht, um seine Anzeige Änderungen entsprechend aktualisiert.|  
  
## <a name="remarks"></a>Hinweise  
 `IView`mehrere Methoden implementiert, die `CWinFormsView` verwendet, um allgemeine Ansicht Benachrichtigungen zu einem gehosteten verwalteten Steuerelement weiterzuleiten. Dies sind [OnInitialUpdate](#oninitialupdate), [OnUpdate](#onupdate) und [OnActivateView](#onactivateview).  
  
 `IView`ähnelt dem [CView](../../mfc/reference/cview-class.md), aber nur für verwaltete Ansichten und Steuerelemente verwendet wird.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  

## <a name="requirements"></a>Anforderungen  
 Header: afxwinforms.h (definiert in der Assembly atlmfc\lib\mfcmifc80.dll)  

## <a name="onactivateview"></a>IView::OnActivateView  
Von MFC aufgerufen, wenn eine Ansicht aktiviert oder deaktiviert wird.
```
void OnActivateView(bool activate);
```
## <a name="parameters"></a>Parameter
`activate`  
Gibt an, ob die Sicht wird aktiviert oder deaktiviert.  

## <a name="oninitialupdate"></a>IView:: OnInitialUpdate
Vom Framework aufgerufen, nachdem die Ansicht zuerst an das Dokument angefügt ist, aber vor dem Beginn der Ansicht angezeigt wird.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a>IView::OnUpdate 
Vom MFC aufgerufen, nachdem die Ansicht Dokument geändert wurde.  
```
void OnUpdate();
```
## <a name="remarks"></a>Hinweise  
Mit dieser Funktion können die Ansicht, um seine Anzeige Änderungen entsprechend aktualisiert.

## <a name="see-also"></a>Siehe auch  
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)


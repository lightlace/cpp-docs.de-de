---
title: IAxWinHostWindowLic Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- No header/ATL::IAxWinHostWindowLic
- No header/ATL::CreateControlLic
- No header/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 6d0e8c0a8ec941c7a7980b81fcd95df08298ea28
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic-Schnittstelle
Diese Schnittstelle bietet Methoden zum Bearbeiten von ein lizenziertes Steuerelement und dessen Host-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|Erstellt ein lizenziertes Steuerelement, und fügt ihn das Hostobjekt.|  
|[CreateControlLicEx](#createcontrollicex)|Erstellt ein lizenziertes Steuerelement, das Hostobjekt fügt ihn und optional einen Ereignishandler eingerichtet.|  
  
## <a name="remarks"></a>Hinweise  
 `IAxWinHostWindowLic`erbt von [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) und fügt Methoden, die die Erstellung von lizenzierte Steuerelemente zu unterstützen.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Elemente dieser Schnittstelle verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL oder C++ zur Verfügung, wie unten dargestellt.  
  
|Der Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 Erstellt ein lizenziertes Steuerelement, initialisiert es und hostet es im Fenster identifizierten `hWnd`.  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrLic`  
 [in] BSTR, die den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
 Beim Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster, ähnlich wie [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrLic`  
 [in] BSTR, die den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, verwendet `IAxWinHostWindowLic::CreateControlLicEx`.











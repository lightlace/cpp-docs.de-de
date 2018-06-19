---
title: IAxWinHostWindowLic Schnittstelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41b4d7891d1bb00f4ee689477d1056dbf2bf28cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362839"
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
 `IAxWinHostWindowLic` erbt von [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) und fügt Methoden, die die Erstellung von lizenzierte Steuerelemente zu unterstützen.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Elemente dieser Schnittstelle verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL oder C++ zur Verfügung, wie unten dargestellt.  
  
|Der Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
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
  
##  <a name="createcontrollicex"></a>  IAxWinHostWindowLic::CreateControlLicEx  
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










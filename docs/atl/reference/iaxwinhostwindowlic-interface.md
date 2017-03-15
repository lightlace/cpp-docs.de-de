---
title: IAxWinHostWindowLic Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 01ff8a7205418583606cbfdb1c028d7097501e00
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic-Schnittstelle
Diese Schnittstelle stellt Methoden zum Bearbeiten von ein lizenziertes Steuerelement und dessen Host-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|Erstellt ein lizenziertes Steuerelement und fügt es dem Host-Objekt.|  
|[CreateControlLicEx](#createcontrollicex)|Erstellt ein lizenziertes Steuerelement, fügt es auf das Hostobjekt und optional einen Ereignishandler eingerichtet.|  
  
## <a name="remarks"></a>Hinweise  
 `IAxWinHostWindowLic`erbt von [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) und fügt die Methoden, die die Erstellung von lizenzierte Steuerelemente unterstützen.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Elemente dieser Schnittstelle verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist als IDL oder C++ verfügbar, wie unten dargestellt.  
  
|Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|Konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="a-namecreatecontrollica--iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
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
 [in] BSTR, der den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
 Das Aufrufen dieser Methode entspricht dem Aufruf [IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `IAxWinHostWindowLic::CreateControlLic`.  
  
##  <a name="a-namecreatecontrollicexa--iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>IAxWinHostWindowLic::CreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster ähnelt [IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol).  
  
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
 [in] BSTR, der den Lizenzschlüssel für das Steuerelement enthält.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) eine Beschreibung der verbleibenden Parameter und Rückgabewert.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel mit `IAxWinHostWindowLic::CreateControlLicEx`.











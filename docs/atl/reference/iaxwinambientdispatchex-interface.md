---
title: IAxWinAmbientDispatchEx Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
dev_langs: C++
helpviewer_keywords: IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fd212417a00335bfc02699cf5e38eeacc6451ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx-Schnittstelle
Diese Schnittstelle implementiert, zusätzliche Umgebungseigenschaften für einen gehosteten Steuerelement.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|Diese Methode wird aufgerufen, um die ambient-Eigenschaft Standardschnittstelle mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.|  
  
## <a name="remarks"></a>Hinweise  
 Schließen Sie diese Schnittstelle in ATL-Anwendungen, die mit den ATL und Host ActiveX-Steuerelemente, insbesondere ActiveX-Steuerelemente, die Umgebungseigenschaften statisch verknüpft sind. Diese Schnittstelle nicht einschließlich wird diese Assertion generiert: "Haben Sie vergessen, die die LIBID an CComModule übergeben"  
  
 Diese Schnittstelle wird von ATL ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Abgeleitet von [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` Fügt eine Methode, die Ihnen ermöglicht, die ambient-Eigenschaft-Schnittstelle, die vom ATL bereitgestellt wird, mit einem Ihrer Wahl zu ergänzen.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) Typinformationen zu laden versucht `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.  
  
 Wenn Sie ATL90.dll, verknüpfen möchten **AXHost** lädt die Typinformationen aus der Typbibliothek in der DLL.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) Weitere Details.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition der diese Schnittstelle ist in verschiedene Formate, verfügbar, wie in der folgenden Tabelle gezeigt.  
  
|Der Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Typbibliothek|ATL.dll|  
|C++|konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Diese Methode wird aufgerufen, um die ambient-Eigenschaft Standardschnittstelle mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pDispatch*  
 Zeiger auf die neue Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetAmbientDispatch` wird aufgerufen, mit einem Zeiger auf eine neue Schnittstelle, die die neue Oberfläche verwendet werden, zum Aufrufen von Eigenschaften oder Methoden, die für das gehostete Steuerelement gefragt werden, ob diese Eigenschaften nicht bereits enthalten sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)

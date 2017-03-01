---
title: IAxWinAmbientDispatchEx Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IAxWinAmbientDispatchEx
- IAxWinAmbientDispatchEx
- ATL::IAxWinAmbientDispatchEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 915514a021aa89b751a49a34cb53b693b9fd0c45
ms.lasthandoff: 02/24/2017

---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx-Schnittstelle
Diese Schnittstelle implementiert, zusätzliche Ambiente-Eigenschaften für ein Steuerelement.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.|  
  
## <a name="remarks"></a>Hinweise  
 Schließen Sie diese Schnittstelle in ATL-Anwendung, die mit ATL und Host-ActiveX-Steuerelemente, insbesondere ActiveX-Steuerelemente, die Umgebungseigenschaften statisch verknüpft sind. Diese Schnittstelle ausschließlich diese Assertion generiert: "Haben Sie vergessen, die LIBID CComModule übergeben"  
  
 Diese Schnittstelle wird von ATL ActiveX-Steuerelement hosten von Objekten verfügbar gemacht. Abgeleitet von [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` Fügt eine Methode, die Sie ergänzen die von ATL mit einem eigenen bereitgestellte Umgebungseigenschaft-Schnittstelle ermöglicht.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) Typinformationen zu laden versucht `IAxWinAmbientDispatch` und `IAxWinAmbientDispatchEx` aus der Typbibliothek, die den Code enthält.  
  
 Wenn Sie eine ATL90.dll, Verknüpfung **AXHost** lädt die Informationen aus der Typbibliothek in der DLL.  
  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für weitere Details.  
  
## <a name="requirements"></a>Anforderungen  
 Die Definition dieser Schnittstelle ist in einer Reihe von Formularen, verfügbar, wie in der folgenden Tabelle dargestellt.  
  
|Definitionstyp|Datei|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Typbibliothek|ATL.dll|  
|C++|konnte IRegistrar (auch in ATLBase.h enthalten)|  
  
##  <a name="a-namesetambientdispatcha--iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Diese Methode wird aufgerufen, um die Standardschnittstelle für die ambient-Eigenschaft mit einer benutzerdefinierten Benutzeroberfläche zu ergänzen.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 *pDispatch*  
 Ein Zeiger auf die neue Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `SetAmbientDispatch` wird aufgerufen, mit der ein Zeiger auf eine neue Schnittstelle, die diese neue Schnittstelle verwendet werden, zum Aufrufen von Eigenschaften oder Methoden, die für die vom gehosteten Steuerelement gefragt werden, ob diese Eigenschaften nicht bereits enthalten sind [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IAxWinAmbientDispatch-Schnittstelle](../../atl/reference/iaxwinambientdispatch-interface.md)


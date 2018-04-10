---
title: Fügen Sie IObjectSafetyImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa7813b694cfea614bc80946d91c8f1bd977e627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iobjectsafetyimpl-class"></a>Fügen Sie IObjectSafetyImpl-Klasse
Diese Klasse stellt eine Standardimplementierung von der `IObjectSafety` Schnittstelle, damit einen Client zum Abrufen und Festlegen eines Objekts Sicherheitsstufen kann.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Gibt die unterstützten Safety-Optionen für das Steuerelement. Kann einer der folgenden Werte sein:  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** die Schnittstelle, die durch identifiziert die [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) Parameter `riid` sicher für Skripting gemacht werden sollen.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** die Schnittstelle, die durch identifiziert die `SetInterfaceSafetyOptions` Parameter `riid` müssen während der Initialisierung für nicht vertrauenswürdige Daten sicher vorgenommen werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Ruft ab, die vom Objekt unterstützten Sicherheitsoptionen als auch die Safety-Optionen, die derzeit für das Objekt festgelegt.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Wird das Objekt für die Initialisierung oder Skripting sicher.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Speichert aktuelle Sicherheitsstufe des Objekts an.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `IObjectSafetyImpl` stellt eine Standardimplementierung von `IObjectSafety`. Die `IObjectSafety` Schnittstelle ermöglicht es einen Client zum Abrufen und Festlegen eines Objekts Sicherheitsstufen. Beispielsweise kann ein Webbrowser aufrufen **IObjectSafety::SetInterfaceSafetyOptions** ein Steuerelement für die Initialisierung sicheren oder sicher für Skripting vornehmen.  
  
 Beachten Sie, dass die Verwendung der [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) Makro mit dem **CATID_SafeForScripting** und **CATID_SafeForInitializing** Komponentenkategorien bietet eine Alternative Möglichkeit der Angabe, dass eine Komponente ist.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Ruft ab, die vom Objekt unterstützten Sicherheitsoptionen als auch die Safety-Optionen, die derzeit für das Objekt festgelegt.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung gibt die entsprechenden Werte für jede Schnittstelle, die von der Implementierung des Objekts unterstützt **IUnknown:: QueryInterface**.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist verantwortlich für seiner eigenen Sicherheitsberechtigungen und, eines beliebigen Objekts delegiert. Der Programmierer muss in Konto Probleme, die durch die Ausführung von Code im Kontext des Benutzers, siteübergreifende Skripterstellung und geeignete Zone wird die Überprüfung durchgeführt.  
  
 Finden Sie unter [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) im Windows SDK.  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 Speichert aktuelle Sicherheitsstufe des Objekts an.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Wird das Objekt sicher für die Initialisierung oder Skripts durch Festlegen der [M_dwCurrentSafety](#m_dwcurrentsafety) Element auf den entsprechenden Wert.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung gibt **E_NOINTERFACE** für jede Schnittstelle nicht unterstützt, durch die Objekt-Implementierung von **IUnknown:: QueryInterface**.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist verantwortlich für seiner eigenen Sicherheitsberechtigungen und, eines beliebigen Objekts delegiert. Der Programmierer muss in Konto Probleme, die durch die Ausführung von Code im Kontext des Benutzers, siteübergreifende Skripterstellung und geeignete Zone wird die Überprüfung durchgeführt.  
  
 Finden Sie unter [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IObjectSafety-Schnittstelle](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

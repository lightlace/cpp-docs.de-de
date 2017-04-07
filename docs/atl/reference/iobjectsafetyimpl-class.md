---
title: "Fügen Sie IObjectSafetyImpl Klasse | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: cff5995555cd069855f9d7becb9eb8367e80c920
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectsafetyimpl-class"></a>Fügen Sie IObjectSafetyImpl-Klasse
Diese Klasse enthält die standardmäßige Implementierung der `IObjectSafety` Schnittstelle, damit einen Client zum Abrufen und Festlegen von Sicherheitsstufen für ein Objekt kann.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Gibt die unterstützten Sicherheitsoptionen für das Steuerelement. Kann einer der folgenden Werte sein:  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** die Schnittstelle, die anhand der [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) Parameter `riid` sicher für Skripting gemacht werden sollen.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** die Schnittstelle, die anhand der `SetInterfaceSafetyOptions` Parameter `riid` sollte während der Initialisierung für nicht vertrauenswürdige Daten vorgenommen werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Ruft die Sicherheitsoptionen, die vom Objekt unterstützten sowie die Sicherheitsoptionen, die derzeit für das Objekt festgelegt.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Wird das Objekt für die Initialisierung oder scripting sicher.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Speichert aktuelle Sicherheitsstufe des Objekts.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `IObjectSafetyImpl` bietet eine Standardimplementierung von `IObjectSafety`. Die `IObjectSafety` Schnittstelle ermöglicht einem Client abrufen und Festlegen von Sicherheitsstufen für ein Objekt. Z. B. ein Webbrowser aufrufen kann **IObjectSafety::SetInterfaceSafetyOptions** an ein Steuerelement sicher für die Initialisierung oder sicher für Skripting zu erstellen.  
  
 Beachten Sie, dass die Verwendung der [IMPLEMENTED_CATEGORY](http://msdn.microsoft.com/library/d898ef34-5684-4709-beb9-7114ddd96674) Makro mit dem **CATID_SafeForScripting** und **CATID_SafeForInitializing** Komponentenkategorien bietet eine alternative Möglichkeit, anzugeben, dass eine Komponente sicher ist.  
  
 **Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Ruft die Sicherheitsoptionen, die vom Objekt unterstützten sowie die Sicherheitsoptionen, die derzeit für das Objekt festgelegt.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung gibt die entsprechenden Werte für jede Schnittstelle, die von der Implementierung des Objekts unterstützt **IUnknown:: QueryInterface**.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist dafür verantwortlich, seine eigene Sicherheit und, die für ein beliebiges Objekt delegiert. Der Programmierer muss in Konto Problemen mit dem Code im Kontext des Benutzers ausgeführt, siteübergreifende Skripts und die geeignete Zone Überprüfung durchgeführt.  
  
 Finden Sie unter [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 Speichert aktuelle Sicherheitsstufe des Objekts.  
  
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
 Die Implementierung gibt **E_NOINTERFACE** für jede Schnittstelle, die von der Implementierung des Objekts nicht unterstützt **IUnknown:: QueryInterface**.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist dafür verantwortlich, seine eigene Sicherheit und, die für ein beliebiges Objekt delegiert. Der Programmierer muss in Konto Problemen mit dem Code im Kontext des Benutzers ausgeführt, siteübergreifende Skripts und die geeignete Zone Überprüfung durchgeführt.  
  
 Finden Sie unter [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IObjectSafety-Schnittstelle](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)


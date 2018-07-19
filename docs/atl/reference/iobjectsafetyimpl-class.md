---
title: IObjectSafetyImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f474c73a63c7eaeb7452e88812180a24d1321df
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881187"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl-Klasse
Diese Klasse stellt eine Standardimplementierung von der `IObjectSafety` Schnittstelle, damit kann einen Client zum Abrufen und Festlegen eines Objekts Sicherheitsstufen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Gibt die unterstützten Safety-Optionen für das Steuerelement. Kann einer der folgenden Werte sein:  
  
- INTERFACESAFE_FOR_UNTRUSTED_CALLER der Schnittstelle von identifiziert die [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) Parameter `riid` sicher für Skripting gemacht werden sollen.  
  
- INTERFACESAFE_FOR_UNTRUSTED_DATA der Schnittstelle von identifiziert die `SetInterfaceSafetyOptions` Parameter `riid` müssen während der Initialisierung für nicht vertrauenswürdige Daten sicher vorgenommen werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Ruft ab, die vom Objekt unterstützten Safety-Optionen sowie die Safety-Optionen, die derzeit für das Objekt festgelegt.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Wird das Objekt für die Initialisierung oder die Skripterstellung sicher.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Speichert das Objekt für die aktuelle Sicherheitsstufe auf.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `IObjectSafetyImpl` stellt eine Standardimplementierung von `IObjectSafety`. Die `IObjectSafety` Schnittstelle ermöglicht es einen Client zum Abrufen und Festlegen eines Objekts Sicherheitsstufen. Z. B. ein Webbrowser aufrufen kann `IObjectSafety::SetInterfaceSafetyOptions` auf ein Steuerelement sicher ist, für die Initialisierung oder sicher für Skripting zu erstellen.  
  
 Beachten Sie, dass die Verwendung der [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) Makro mit dem Komponentenkategorien CATID_SafeForScripting und CATID_SafeForInitializing bietet eine alternative Möglichkeit der Angabe, dass eine Komponente sicher ist.  
  
 **Verwandte Artikel** [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Ruft ab, die vom Objekt unterstützten Safety-Optionen sowie die Safety-Optionen, die derzeit für das Objekt festgelegt.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung gibt zurück, die entsprechenden Werte für jede Schnittstelle, die von der Implementierung des Objekts unterstützt `IUnknown::QueryInterface`.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist verantwortlich für die eigene Sicherheit und, die für ein beliebiges Objekt delegiert. Der Programmierer muss in kontoprobleme im Zusammenhang mit Code im Kontext des Benutzers ausgeführt, siteübergreifendes scripting und führen Sie die geeignete Zone zu überprüfen.  
  
 Finden Sie unter [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) in das Windows SDK.  
  
##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety  
 Speichert das Objekt für die aktuelle Sicherheitsstufe auf.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Stellt das Objekt sicher für die Initialisierung oder die Skripterstellung durch Festlegen der [M_dwCurrentSafety](#m_dwcurrentsafety) Member auf den entsprechenden Wert.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung wird E_NOINTERFACE zurückgegeben, für jede Schnittstelle, die von der Implementierung des Objekts nicht unterstützt `IUnknown::QueryInterface`.  
  
> [!IMPORTANT]
>  Jedes Objekt, das unterstützt `IObjectSafety` ist verantwortlich für die eigene Sicherheit und, die für ein beliebiges Objekt delegiert. Der Programmierer muss in kontoprobleme im Zusammenhang mit Code im Kontext des Benutzers ausgeführt, siteübergreifendes scripting und führen Sie die geeignete Zone zu überprüfen.  
  
 Finden Sie unter [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IObjectSafety-Schnittstelle](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

---
title: Klasse CAutoRevertImpersonation | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f86f1e5067583b3c4c615c8ca3095e8b67b3fffe
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation-Klasse
Diese Klasse wird zurückgesetzt [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekte in einem nonimpersonating Zustand, wenn sie den Gültigkeitsbereich verlässt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Erstellt ein `CAutoRevertImpersonation` Objekt|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Das Objekt zerstört und Access token Identitätswechsel zurückgesetzt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Automatisiert den Identitätswechsel Zurücksetzen eines Zugriffstokens.|  
|[CAutoRevertImpersonation::Detach](#detach)|Bricht den automatischen Identitätswechsel zurücksetzen.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Ruft die diesem Objekt zugeordneten aktuellen Access token ab.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das beschreibt den Sicherheitskontext für einen Prozess oder Thread, und jeder Benutzer ein Windows NT oder Windows 2000-System angemeldet zugeordnet ist. Dieser Zugangs-Token dargestellt werden können, mit der `CAccessToken` Klasse.  
  
 Manchmal ist es erforderlich, Zugriffstoken Identität annehmen. Diese Klasse wird als Annehmlichkeit bereitgestellt, aber den Identitätswechsel des Zugangs-Token wird nicht ausgeführt; Es führt nur die automatischen Stornierung in einem nonimpersonated Zustand. Dies ist da Identitätswechsel token Zugriff auf unterschiedliche Weise ausgeführt werden kann.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 Automatisiert den Identitätswechsel Zurücksetzen eines Zugriffstokens.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pAT`  
 Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt automatisch zurückgesetzt werden  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte nur verwendet werden, wenn die [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) Objekt erstellt wurde, mit einer NULL- `CAccessToken` -Zeiger ist, oder wenn [trennen](#detach) zuvor aufgerufen wurde. In einfachen Fällen ist es nicht erforderlich, diese Methode zu verwenden.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 Erstellt ein `CAutoRevertImpersonation`-Objekt.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pAT`  
 Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt automatisch zurückgesetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Der aktuelle Identitätswechsel des Zugriffstokens sollten separat ausgeführt werden, von und vorzugsweise vor dem Erstellen des ein `CAutoRevertImpersonation` Objekt. Dieser Identitätswechsel wird zurückgesetzt werden automatisch bei der `CAutoRevertImpersonation` -Objekt den Gültigkeitsbereich verlässt.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 Das Objekt zerstört und Access token Identitätswechsel zurückgesetzt.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Zurückgesetzt jeder Identitätswechsel, der derzeit für die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt bei der Konstruktion oder über die [Anfügen](#attach) Methode. Wenn kein `CAccessToken` ist verknüpft, der Destruktor hat keine Auswirkung.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 Bricht den automatischen Identitätswechsel zurücksetzen.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse der zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen **trennen** verhindert, dass die `CAutoRevertImpersonation` Objekt aus Wiederherstellen jeder Identitätswechsel, der derzeit für die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt, das mit diesem Objekt zugeordnet. `CAutoRevertImpersonation`keine Auswirkung zerstört oder auf demselben oder einem anderen neu zugeordnet werden können `CAccessToken` -Objekt unter Verwendung der [Anfügen](#attach).  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 Ruft die diesem Objekt zugeordneten aktuellen Access token ab.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse der zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode für die Zwecke aufgerufen wird, die das Zurücksetzen eines Identitätswechsels des enthalten die `CAccessToken` -Objekt, das [trennen](#detach) Methode sollte stattdessen verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLSecurity-Beispiel](../../visual-cpp-samples.md)   
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)


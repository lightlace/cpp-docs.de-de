---
title: CAutoRevertImpersonation Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 942c446fc64bb7e4210bc82e21fc2511ae01503a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359506"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation-Klasse
Diese Klasse wird zurückgesetzt [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekte in einem nonimpersonating Zustand, wenn sie den Gültigkeitsbereich verlässt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Erstellt ein `CAutoRevertImpersonation` Objekt|  
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|Das Objekt zerstört und Access token Identitätswechsel zurückgesetzt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Automatisiert den Identitätswechsel Zurücksetzen des ein Zugriffstoken an.|  
|[CAutoRevertImpersonation::Detach](#detach)|Bricht den automatischen Identitätswechsel eine neue Version zuweisen.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Ruft die diesem Objekt zugeordneten aktuellen Access token ab.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ein Objekt, das den Sicherheitskontext für einen Prozess oder Thread beschreibt und erhält jeder Benutzer ein Windows NT oder Windows 2000-System angemeldet ist. Diese Zugriffstoken dargestellt werden können, mit der `CAccessToken` Klasse.  
  
 Manchmal ist es erforderlich, für den Identitätswechsel Zugriffstoken. Diese Klasse wird als Annehmlichkeit bereitgestellt, aber es führt keine Zugriffstoken für den Identitätswechsel; Sie führt nur die automatisch eine neue Version zuweisen zum Zustand "nonimpersonated". Dies liegt daran tokenzugriff Identitätswechsel auf verschiedene Weise ausgeführt werden kann.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="attach"></a>  CAutoRevertImpersonation::Attach  
 Automatisiert den Identitätswechsel Zurücksetzen des ein Zugriffstoken an.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pAT`  
 Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt automatisch zurückgesetzt werden  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sollte nur verwendet werden, wenn die [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) Objekt erstellt wurde, mit einem NULL- `CAccessToken` -Zeiger ist, oder wenn [trennen](#detach) zuvor aufgerufen wurde. In einfachen Fällen ist es nicht notwendig, diese Methode zu verwenden.  
  
##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation  
 Erstellt ein `CAutoRevertImpersonation`-Objekt.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pAT`  
 Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt automatisch zurückgesetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Der tatsächliche Identitätswechsel des Zugriffstokens sollten separat ausgeführt werden, aus, und zwar nach Möglichkeit vor der Erstellung von einem `CAutoRevertImpersonation` Objekt. Dieser Identitätswechsel wird zurückgesetzt werden automatisch bei der `CAutoRevertImpersonation` Objekt den Gültigkeitsbereich verlässt.  
  
##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation  
 Das Objekt zerstört und Access token Identitätswechsel zurückgesetzt.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Setzt alle Identitätswechsel derzeit wirksamen für zurück die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt bereitgestellt werden, bei der Erstellung oder über die [Anfügen](#attach) Methode. Wenn kein `CAccessToken` ist verknüpft, der Destruktor hat keine Auswirkungen.  
  
##  <a name="detach"></a>  CAutoRevertImpersonation::Detach  
 Bricht den automatischen Identitätswechsel eine neue Version zuweisen.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von **trennen** wird verhindert, dass die `CAutoRevertImpersonation` -Sitzungsobjekts alle Identitätswechsel derzeit wirksamen für die Wiederherstellung der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt, das mit diesem Objekt zugeordnet. `CAutoRevertImpersonation` hat keine Auswirkungen zerstört oder erneut an dieselbe oder eine andere verbunden werden können `CAccessToken` -Objekt mit [Anfügen](#attach).  
  
##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken  
 Ruft die diesem Objekt zugeordneten aktuellen Access token ab.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode für die Zwecke aufgerufen wird, die das Zurücksetzen eines Identitätswechsels des enthalten die `CAccessToken` -Objekt, das [trennen](#detach) Methode sollte stattdessen verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLSecurity-Beispiel](../../visual-cpp-samples.md)   
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

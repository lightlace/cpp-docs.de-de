---
title: "Gerät Kontext globale Funktionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8c71781519b965717acbcefab6fe6a183686caef
ms.lasthandoff: 02/24/2017

---
# <a name="device-context-global-functions"></a>Gerät Kontext globale Funktionen
Diese Funktion erstellt einen Gerätekontext für ein bestimmtes Gerät.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Erstellt einen Gerätekontext.|  
  
##  <a name="a-nameatlcreatetargetdca--atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Erstellt einen Gerätekontext für das Gerät gemäß den [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Struktur.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Parameter  
 *hdc*  
 [in] Das vorhandene-Handle für einen Gerätekontext, oder **NULL**.  
  
 `ptd`  
 [in] Ein Zeiger auf die **DVTARGETDEVICE** -Struktur, die Informationen über das Zielgerät enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für einen Gerätekontext für das Gerät gemäß den **DVTARGETDEVICE**. Wenn kein Gerät angegeben ist, gibt das Handle an das Standardgerät für die Anzeige zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Struktur **NULL** und *Hdc* ist **NULL**, erstellt einen Gerätekontext für das Standard-Anzeigegerät.  
  
 Wenn *Hdc* nicht **NULL** und `ptd` ist **NULL**, die Funktion gibt die vorhandene *Hdc*.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
   
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)


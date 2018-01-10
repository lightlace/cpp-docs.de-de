---
title: "Globale Kontextfunktionen Gerät | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlwin/ATL::AtlCreateTargetDC
dev_langs: C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9aa685604580423262ab694d1285897cd29eef63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="device-context-global-functions"></a>Gerät Kontext globale Funktionen
Diese Funktion erstellt einen Gerätekontext für ein bestimmtes Gerät.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Erstellt einen Gerätekontext.|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Erstellt einen Gerätekontext für das Gerät gemäß den [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) Struktur.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Parameter  
 *hdc*  
 [in] Das vorhandene Handle für einen Gerätekontext oder **NULL**.  
  
 `ptd`  
 [in] Ein Zeiger auf die **DVTARGETDEVICE** -Struktur, die Informationen über das Zielgerät enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für einen Gerätekontext für das Gerät gemäß den **DVTARGETDEVICE**. Wenn kein Gerät angegeben ist, gibt das Handle an das Standardgerät für die Anzeige zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Struktur **NULL** und *Hdc* ist **NULL**, erstellt einen Gerätekontext für das Standardgerät für die Anzeige.  
  
 Wenn *Hdc* nicht **NULL** und `ptd` ist **NULL**, die Funktion gibt den vorhandenen *Hdc*.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
   
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

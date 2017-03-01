---
title: _ATL_COM_MODULE70 Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
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
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 503c2a29cf0e70020b012911c51b056f00562374
ms.lasthandoff: 02/24/2017

---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70-Struktur
Verwendung durch COM-bezogene Code in ATL  
  
## <a name="syntax"></a>Syntax  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>Mitglieder  
 `cbSize`  
 Die Größe der Struktur, die für die Versionskontrolle verwendet.  
  
 `m_hInstTypeLib`  
 Der Handle-Instanz, die die Typbibliothek für dieses Modul.  
  
 **m_ppAutoObjMapFirst**  
 Die Adresse des Arrayelements, die den Beginn der Einträge in der Objekt-Zuordnung für dieses Modul.  
  
 **m_ppAutoObjMapLast**  
 Die Adresse des Arrayelements, der das Ende der Objekt-Zuordnungseinträge für dieses Modul.  
  
 `m_csObjMap`  
 Kritischen Abschnitt zum Zugriff auf den Zuordnungseinträgen Objekt zu serialisieren. Wird intern verwendet, ATL  
  
## <a name="remarks"></a>Hinweise  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) ist definiert als Typedef von `_ATL_COM_MODULE70`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)







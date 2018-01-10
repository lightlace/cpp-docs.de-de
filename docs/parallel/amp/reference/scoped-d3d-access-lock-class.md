---
title: scoped_d3d_access_lock-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_d3d_access_lock
- AMPRT/scoped_d3d_access_lock
- AMPRT/concurrency::direct3d::scoped_d3d_access_lock::scoped_d3d_access_lock
dev_langs: C++
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37dadc932701354de317d253a39bd2f2ee71a495
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scopedd3daccesslock-class"></a>scoped_d3d_access_lock-Klasse
RAII-Wrapper für eine D3D-Zugriffssperre auf einem accelerator_view-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
class scoped_d3d_access_lock;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scoped_d3d_access_lock-Konstruktor](#ctor)|Überladen. Erstellt ein `scoped_d3d_access_lock`-Objekt. Die Sperre wird aufgehoben, wenn dieses Objekt den Gültigkeitsbereich verlässt.|  
|[~ scoped_d3d_access_lock-Destruktor](#dtor)|Gibt die D3D-Zugriffssperre auf dem zugeordneten `accelerator_view`-Objekt frei.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator=](#operator_eq)|Übernimmt den Besitz einer Sperre eines anderen `scoped_d3d_access_lock`-Objekts.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scoped_d3d_access_lock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Concurrency:: Direct3D  

##  <a name="ctor"></a>scoped_d3d_access_lock 

 Erstellt ein `scoped_d3d_access_lock`-Objekt. Die Sperre wird aufgehoben, wenn dieses Objekt den Gültigkeitsbereich verlässt.  
 
```  
explicit scoped_d3d_access_lock(// [1] constructor  
    accelerator_view& _Av);

 
explicit scoped_d3d_access_lock(// [2] constructor  
    accelerator_view& _Av,  
    adopt_d3d_access_lock_t _T);

 
scoped_d3d_access_lock(// [3] move constructor  
    scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Av`  
 Das `accelerator_view`-Objekt, für das die Sperre übernommen wird.  
  
 `_T`  
 Das `adopt_d3d_access_lock_t`-Objekt.  
  
 `_Other`  
 Das `scoped_d3d_access_lock`-Objekt, dessen vorhandene Sperre aufgehoben werden soll.  
  
## <a name="construction"></a>Konstruktion  
 [1]-Konstruktor  
 Ruft eine D3D-Zugriffssperre auf dem angegebenen ["accelerator_view"](accelerator-view-class.md) Objekt. Die Konstruktion wird blockiert, bis die Sperre abgerufen wird.  
  
 [2]-Konstruktor  
 Übernehmen Sie eine D3D-Zugriffssperre aus der angegebenen ["accelerator_view"](accelerator-view-class.md) Objekt.  
  
 [3]-Bewegungskonstruktor  
 Hebt eine vorhandene D3D-Zugriffssperre eines anderen `scoped_d3d_access_lock`-Objekts auf. Die Konstruktion wird nicht blockiert.  

  
##  <a name="dtor"></a>~ scoped_d3d_access_lock 

 Gibt die D3D-Zugriffssperre auf dem zugeordneten `accelerator_view`-Objekt frei.  
  
```  
~scoped_d3d_access_lock();
```  
## <a name="operator_eq"></a>Operator = 

Übernimmt den Besitz einer D3D-Zugriffssperre eines anderen `scoped_d3d_access_lock`-Objekts und hebt die vorherige Sperre auf.  
 
```  
scoped_d3d_access_lock& operator= (scoped_d3d_access_lock&& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das accelerator_view-Objekt, von dem die D3D-Zugriffssperre verschoben werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf dieses `scoped_accelerator_view_lock`-Objekt.  

## <a name="see-also"></a>Siehe auch  
 [Concurrency::direct3d Namespace](concurrency-direct3d-namespace.md)

---
title: CComAutoDeleteCriticalSection Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs: C++
helpviewer_keywords: CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0a0c5fdd45e819105a3f47e98c02bb5ad3d51be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Hinweise  
 `CComAutoDeleteCriticalSection`leitet sich von der Klasse [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Allerdings `CComAutoDeleteCriticalSection` überschreibt die [Begriff](ccomsafedeletecriticalsection-class.md#term) Methode, um `private` Zugriff, der erzwingt die internen Speicher Cleanup erfolgen nur, wenn Instanzen dieser Klasse immer innerhalb des Gültigkeitsbereichs oder explizit aus dem Arbeitsspeicher gelöscht werden.  

  
 Diese Klasse führt keine zusätzlichen Methoden über seine Basisklasse. Finden Sie unter [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) und ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) für Weitere Informationen zu kritischen Abschnitt Hilfsklassen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
## <a name="see-also"></a>Siehe auch  
 [CComSafeDeleteCriticalSection-Klasse](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

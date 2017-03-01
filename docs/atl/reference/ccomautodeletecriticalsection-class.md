---
title: Klasse CComAutoDeleteCriticalSection | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComAutoDeleteCriticalSection
- CComAutoDeleteCriticalSection
- ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: eb53a0966d29759bbe7513f6042f72a280801707
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection-Klasse
Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Hinweise  
 `CComAutoDeleteCriticalSection`leitet sich von der Klasse [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Allerdings `CComAutoDeleteCriticalSection` überschreibt die [Begriff](ccomsafedeletecriticalsection-class.md#term) Methode, um `private` Zugriff, was die erzwingt die internen Speicher Cleanup erfolgen nur, wenn Instanzen dieser Klasse verlassen den Gültigkeitsbereich oder explizit aus dem Speicher gelöscht werden.  

  
 Diese Klasse führt keine zusätzlichen Methoden über seine Basisklasse. Finden Sie unter [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) und ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) Weitere Informationen zu kritischen Abschnitt Hilfsklassen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
## <a name="see-also"></a>Siehe auch  
 [CComSafeDeleteCriticalSection-Klasse](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)


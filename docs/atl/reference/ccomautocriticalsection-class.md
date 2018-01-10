---
title: CComAutoCriticalSection Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs: C++
helpviewer_keywords: CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d12abfceeebeb1cac89b510c14d7a9211173406e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection-Klasse
`CComAutoCriticalSection`Stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Der Konstruktor.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Der Destruktor.|  
  
## <a name="remarks"></a>Hinweise  
 `CComAutoCriticalSection`Klasse ähnelt ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md), mit Ausnahme von `CComAutoCriticalSection` automatisch die kritischen Abschnittsobjekt im Konstruktor initialisiert.  
  
 Verwenden Sie in der Regel `CComAutoCriticalSection` über die `typedef` Namen [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Dieser Name verweist auf `CComAutoCriticalSection` Wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  

  
 Die `Init` und `Term` Methoden aus ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) sind nicht verfügbar, wenn Sie diese Klasse verwenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Der Konstruktor.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die Win32-Funktion [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), die die kritischen Abschnittsobjekt initialisiert.  
  
##  <a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 Der Destruktor.  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor ruft [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), die alle von der kritischen Abschnittsobjekt verwendeten Systemressourcen frei.  
  
## <a name="see-also"></a>Siehe auch  
 [CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)

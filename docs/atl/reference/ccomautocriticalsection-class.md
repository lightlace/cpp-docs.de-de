---
title: Klasse CComAutoCriticalSection | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComAutoCriticalSection
- ATL::CComAutoCriticalSection
- CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
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
ms.openlocfilehash: 9f58a4cfd02af09a05b625a7e02b574b672adade
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection-Klasse
`CComAutoCriticalSection`Stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Der Konstruktor.|  
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Der Destruktor.|  
  
## <a name="remarks"></a>Hinweise  
 `CComAutoCriticalSection`Klasse ähnelt ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md), mit Ausnahme von `CComAutoCriticalSection` automatisch das Objekt des kritischen Abschnitts im Konstruktor initialisiert.  
  
 Normalerweise verwenden Sie `CComAutoCriticalSection` über die `typedef` Namen [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Dieser Name verweist auf `CComAutoCriticalSection` Wenn [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.  

  
 Die `Init` und `Term` Methoden ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md) sind nicht verfügbar, wenn Sie diese Klasse verwenden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 ["CComCriticalSection"](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="a-nameccomautocriticalsectiona--ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Der Konstruktor.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Hinweise  
 Ruft die Win32-Funktion [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), die Objekt des kritischen Abschnitts initialisiert.  
  
##  <a name="a-namedtora--ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>CComAutoCriticalSection:: ~ CComAutoCriticalSection  
 Der Destruktor.  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor ruft [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), die alle vom Objekt kritischen Abschnitts verwendete Systemressourcen frei.  
  
## <a name="see-also"></a>Siehe auch  
 [CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 ["CComCriticalSection"-Klasse](../../atl/reference/ccomcriticalsection-class.md)


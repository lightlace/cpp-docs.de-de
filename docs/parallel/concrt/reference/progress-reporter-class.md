---
title: Progress_reporter-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::progress_reporter
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: c6b4dfee5b5f9df98a36fcdac116182ced4cbe30
ms.lasthandoff: 02/24/2017

---
# <a name="progressreporter-class"></a>progress_reporter-Klasse
Die Status-Reporter-Klasse ermöglicht Benachrichtigungen zum Status der Berichterstellung eines bestimmten Typs. Jedes progress_reporter-Objekt ist an eine bestimmte asynchrone Aktion bzw. einen Vorgang gebunden.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename _ProgressType>
class progress_reporter;
```  
  
#### <a name="parameters"></a>Parameter  
 `_ProgressType`  
 Der Nutzlasttyp jeder Statusbenachrichtigung, die vom Status-Reporter gemeldet wird.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Progress_reporter-Konstruktor](#ctor)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Bericht-Methode](#report)|Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Typ ist nur für Windows Store-Apps verfügbar.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `progress_reporter`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-progressreporter"></a><a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="a-namereporta-report"></a><a name="report"></a>Bericht 

 Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `val`  
 Die Nutzlast, über die mit einer Statusbenachrichtigung berichtet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)


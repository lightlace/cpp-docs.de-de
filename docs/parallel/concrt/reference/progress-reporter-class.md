---
title: Progress_reporter-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d5d4dc98c4fb411a4d63fdfad5049cf0df723bec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686564"
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
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Bericht](#report)|Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Typ ist nur für Windows-Runtime-apps verfügbar.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `progress_reporter`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a> Bericht 

 Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `val`  
 Die Nutzlast, über die mit einer Statusbenachrichtigung berichtet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

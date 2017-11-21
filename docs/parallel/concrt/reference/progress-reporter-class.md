---
title: Progress_reporter-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs: C++
helpviewer_keywords: progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a72250bcb35b625276d0b8692ce1ec9d13a20ade
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 Dieser Typ ist nur für Windows Store-Apps verfügbar.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `progress_reporter`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "ppltasks.h"  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a>Bericht 

 Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `val`  
 Die Nutzlast, über die mit einer Statusbenachrichtigung berichtet werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

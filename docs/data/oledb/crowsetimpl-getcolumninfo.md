---
title: 'CRowsetImpl:: GetColumnInfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18ed527d47b8bfb4ffa64c88597cc2e241ad9852
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
Ruft die Spalteninformationen für einen bestimmten Client-Anforderung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pv`  
 [in] Ein Zeiger auf des Benutzers `CRowsetImpl` abgeleitete Klasse.  
  
 `pcCols`  
 [in] Ein Zeiger (Ausgabe), um die Anzahl der Spalten zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen statischen **ATLCOLUMNINFO-Struktur** Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist eine erweiterte Außerkraftsetzung.  
  
 Diese Methode wird von mehreren basisimplementierung Klassen zum Abrufen von Spalteninformationen für einen bestimmten Client-Anforderung aufgerufen. In der Regel würden diese Methode aufgerufen werden, indem `IColumnsInfoImpl`. Wenn Sie diese Methode überschreiben, müssen Sie eine Version der Methode im Platzieren Ihrer `CRowsetImpl`-Klasse. Da die Methode in einer Klasse nicht vorlagenbasiert platziert werden kann, müssen Sie ändern `pv` an die entsprechende `CRowsetImpl`-Klasse abgeleitet.  
  
 Das folgende Beispiel zeigt **GetColumnInfos** Verwendung. In diesem Beispiel **CRowset** ist eine `CRowsetImpl`-Klasse. Um das Überschreiben `GetColumnInfo` für alle Instanzen dieser Klasse, platzieren Sie die folgende Methode in der **CRowset** Klassendefinition:  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)
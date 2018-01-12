---
title: CEnumerator-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CEnumerator
dev_langs: C++
helpviewer_keywords: CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a64ac02e7b16bfab70966ffaf2a1897ae955f8c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cenumerator-class"></a>CEnumerator-Klasse
Verwendet eine OLE DB-Enumerator-Objekt, das macht die [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) -Schnittstelle zur Rückgabe eines Rowsets, die alle Datenquellen und Enumeratoren beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Suchen](../../data/oledb/cenumerator-find.md)|Durchsucht verfügbaren Anbieter (Datenquellen) mit dem angegebenen Namen gesucht.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Ruft die `IMoniker` Schnittstelle für den aktuellen Datensatz.|  
|[Öffnen](../../data/oledb/cenumerator-open.md)|Öffnet den Enumerator.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können Abrufen der **ISourcesRowset** Daten indirekt von dieser Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:**atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Dieses Beispiel](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)
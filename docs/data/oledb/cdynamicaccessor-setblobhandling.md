---
title: 'CDynamicAccessor:: Setblobhandling | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs:
- C++
helpviewer_keywords:
- SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 921ec36872d10c5109eeeb694cdf0fe1394022df
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
Legt das BLOB Behandlung von Wert für die aktuelle Zeile fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>Parameter  
 `eBlobHandling`  
 Gibt an, wie die BLOB-Daten behandelt werden. Die folgenden Werte sind möglich:  
  
-   **DBBLOBHANDLING_DEFAULT**: Behandeln von Spaltendaten, die größer als `nBlobSize` (wie Festlegen von `SetBlobSizeLimit`) als BLOB-Daten, und rufen Sie sie über ein `ISequentialStream` oder `IStream` Objekt. Diese Option versucht, jede Spalte mit Daten, die größer als binden `nBlobSize` oder als aufgelisteten **DBTYPE_IUNKNOWN** als BLOB-Daten.  
  
-   **DBBLOBHANDLING_NOSTREAMS**: Behandeln von Spaltendaten, die größer als `nBlobSize` (entsprechend der Festlegung durch `SetBlobSizeLimit`) als BLOB-Daten und durch Verweis im Anbieter zugeordnet, Consumer-eigenen Arbeitsspeicher abrufen. Diese Option eignet sich für Tabellen, die mehr als eine BLOB-Spalte aufweisen, und der Anbieter unterstützt nur ein `ISequentialStream` Objekt pro Accessor.  
  
-   **DBBLOBHANDLING_SKIP**: Skip (nicht gebunden) Spalten qualifizierenden BLOBs enthält (der Accessor nicht binden oder Abrufen des Werts für die Spalte aber es werden weiterhin abgerufen, die Spalte Status und Länge).  
  
## <a name="remarks"></a>Hinweise  
 Rufen Sie `SetBlobHandling` vor dem Aufruf **öffnen**.  
  
 Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt die Behandlung von Wert BLOB **DBBLOBHANDLING_DEFAULT**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)
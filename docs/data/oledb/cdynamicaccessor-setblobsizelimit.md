---
title: CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2fac05c1380e2b612cb39994716387d99bef237
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
Legt die maximale BLOB-Größe in Bytes fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nBlobSize`  
 Gibt das Größenlimit für BLOBs an.  
  
## <a name="remarks"></a>Hinweise  
 Legt die maximale BLOB-Größe in Bytes fest. Spaltendaten, die größer als dieser Wert werden als BLOB behandelt. Einige Anbieter bieten extrem große Größen für Spalten (z. B. 2 GB). Anstatt zu versuchen, Zuweisen von Arbeitsspeicher für eine Spalte dieser Größe, würde in der Regel versucht, diese Spalten als BLOBs zu binden. Auf diese Weise müssen Sie nicht sämtlichen Arbeitsspeicher zuzuweisen, aber Sie können weiterhin alle Daten ohne abgeschnitten zu lesen. Es gibt jedoch einige Fälle, in dem gewünschten erzwungen `CDynamicAccessor` große Spalten in ihren systemeigenen Datentypen zu binden. Zu diesem Zweck rufen `SetBlobSizeLimit` vor dem Aufruf **öffnen**.  
  
 Die Konstruktormethode [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) legt die maximale BLOB-Größe auf einen Standardwert von 8.000 Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)
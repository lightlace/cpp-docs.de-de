---
title: 'CDynamicAccessor:: Setblobsizelimit | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs: C++
helpviewer_keywords: SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d7d522663bf08ede5a83e262044bc8f6846fde1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
Legt die maximale BLOB-Größe in Bytes fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void SetBlobSizeLimit(  
   DBLENGTH nBlobSize   
);  
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
---
title: 'CDynamicAccessor:: CDynamicAccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
dev_langs: C++
helpviewer_keywords: CDynamicAccessor class, constructor
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3f063652b95cc5e778d7e1ffcbc809b9425f5425
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorcdynamicaccessor"></a>CDynamicAccessor::CDynamicAccessor
Instanziiert und initialisiert die `CDynamicAccessor` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      CDynamicAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `eBlobHandling`  
 Gibt an, wie die Daten binary large Object (BLOB) behandelt werden. Der Standardwert ist **DBBLOBHANDLING_DEFAULT**. Finden Sie unter [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) eine Beschreibung der **DBBLOBHANDLINGENUM** Werte.  
  
 `nBlobSize`  
 Die maximale BLOB-Größe in Byte; Spaltendaten über diesem Wert werden als BLOB behandelt. Der Standardwert ist 8.000 sein. Finden Sie unter [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) für Details.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie zum Initialisieren des Konstruktors verwenden die `CDynamicAccessor` -Objekt, können Sie angeben, wie es BLOBs gebunden werden. BLOBs können Binärdaten, z. B. Grafiken, Sound- oder kompilierten Code enthalten. Das Standardverhalten besteht darin Spalten mehr als 8.000 Byte als BLOBs behandeln und versuchen sie zum Binden einer `ISequentialStream` Objekt. Allerdings können Sie einen anderen Wert so, dass die BLOB-Größe angeben.  
  
 Sie können auch angeben, wie `CDynamicAccessor` Spaltendaten, die als BLOB-Daten qualifiziert behandelt: kann er auf die Standardweise BLOB-Daten verarbeiten, können Sie überspringen (nicht gebunden) BLOB-Daten; oder es kann BLOB-Daten im Anbieter reservierten Speicher binden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)
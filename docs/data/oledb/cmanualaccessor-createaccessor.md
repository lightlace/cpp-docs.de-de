---
title: 'CManualAccessor:: CreateAccessor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f313e6d2b13a03a91295c75d52e4e77d5dfda22b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Belegt Speicher für die Spalte Strukturen binden, und die spaltendatenmember initialisiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nBindEntries`  
 [in] Anzahl der Spalten. Diese Anzahl übereinstimmen, die Anzahl der Aufrufe an die [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) Funktion.  
  
 `pBuffer`  
 [in] Ein Zeiger auf den Puffer, in denen die Ausgabespalten gespeichert sind.  
  
 `nBufferSize`  
 [in] Die Größe des Puffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird vor dem Aufrufen der `CManualAccessor::AddBindEntry` Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer-Beispiel](../../visual-cpp-samples.md)
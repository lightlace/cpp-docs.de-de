---
title: 'CManualAccessor:: Createparameteraccessor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CreateParameterAccessor method
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6f217548bb968d06a28278726632724634cc7bb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097730"
---
# <a name="cmanualaccessorcreateparameteraccessor"></a>CManualAccessor::CreateParameterAccessor
Belegt Speicher für den Parameter Strukturen binden, und die Parameterdatenmember initialisiert.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT CreateParameterAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nBindEntries`  
 [in] Anzahl der Spalten.  
  
 `pBuffer`  
 [in] Ein Zeiger auf den Puffer, in dem die Eingabespalten gespeichert sind.  
  
 `nBufferSize`  
 [in] Die Größe des Puffers in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen mit dieser Funktion werden vor dem Aufruf [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CManualAccessor-Klasse](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)   
 [CManualAccessor::AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)
---
title: 'Ftmbase::: UnmarshalInterface-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3710e84a9f7680b56f461029f279a659a5c14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase:::UnmarshalInterface-Methode
Initialisiert einen neu erstellten Proxy, und gibt einen Schnittstellenzeiger, der diesem Proxy zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pStm`  
 Zeiger auf der Stream, aus dem Schnittstellenzeiger rückgängig gemacht werden.  
  
 `riid`  
 Verweis auf den Bezeichner der Schnittstelle, die rückgängig gemacht werden.  
  
 `ppv`  
 Wenn dieser Vorgang abgeschlossen wird, die Adresse einer Zeigervariablen, die den Schnittstellenzeiger in angeforderte empfängt `riid`. Wenn dieser Vorgang erfolgreich ist, wird *`ppv` enthält den angeforderten Schnittstellenzeiger auf der Schnittstelle, die rückgängig gemacht werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_NOINTERFACE oder E_FAIL zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)
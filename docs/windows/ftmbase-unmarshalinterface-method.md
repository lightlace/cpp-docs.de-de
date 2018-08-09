---
title: 'Ftmbase::: UnmarshalInterface-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a1991454daa76fcf7878a7487080124b5a34dbeb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644033"
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase:::UnmarshalInterface-Methode
Initialisiert einen neu erstellten Proxy, und gibt einen Schnittstellenzeiger zurück, auf diesen Proxy.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
### <a name="parameters"></a>Parameter  
 *pStm*  
 Zeiger auf der Stream, aus dem der Schnittstellenzeiger auf das Marshalling rückgängig gemacht werden.  
  
 *riid*  
 Verweis auf den Bezeichner der Schnittstelle an Marshalling rückgängig gemacht werden.  
  
 *ppv*  
 Wenn dieser Vorgang abgeschlossen ist, die Adresse einer Zeigervariablen, die die im angeforderten Schnittstellenzeiger empfängt *Riid*. Wenn dieser Vorgang erfolgreich ist, ist **Ppv* enthält den angeforderten Schnittstellenzeiger, der die Schnittstelle für das Marshalling rückgängig gemacht werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_NOINTERFACE oder E_FAIL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)
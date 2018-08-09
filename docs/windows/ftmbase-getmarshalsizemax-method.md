---
title: 'Ftmbase:: GetMarshalSizeMax-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs:
- C++
helpviewer_keywords:
- GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7976d0ea22a0bf6f59b020f892d407c4721b9a7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652356"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax-Methode
Rufen Sie die obere Grenze für die Anzahl von Bytes erforderlich, um den angegebenen Schnittstellenzeiger für das angegebene Objekt gemarshallt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
### <a name="parameters"></a>Parameter  
 *riid*  
 Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll.  
  
 *PV*  
 Der Schnittstellenzeiger, gemarshallt werden soll; NULL kann sein.  
  
 *dwDestContext*  
 Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.  
  
 Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.  
  
 Rückgängigmachen des Marshallens kann derzeit, die entweder in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.  
  
 *pvDestContext*  
 Für die zukünftige Verwendung reserviert. NULL muss sein.  
  
 *mshlflags*  
 Flag, das angibt, ob die Daten gemarshallt werden zurück an den Clientprozess übertragen werden – der Normalfall – oder in einer globalen Tabelle, in dem sie, indem mehrere Clients abgerufen werden geschrieben. Geben Sie einen oder mehrere MSHLFLAGS-Enumerationswerte.  
  
 *pSize*  
 Wenn dieser Vorgang abgeschlossen ist, Zeiger auf die obere Grenze für die Menge der Daten in den Marshalling Stream geschrieben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_FAIL oder E_NOINTERFACE an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)
---
title: 'Ftmbase:: GetMarshalSizeMax-Methode | Microsoft Docs'
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
ms.openlocfilehash: 5a298e63bc67dadf33a5e653d0eecf165a530d82
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873793"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax-Methode
Rufen Sie die obere Grenze für die Anzahl der Bytes, die erforderlich sind, um den angegebenen Schnittstellenzeiger auf das angegebene Objekt zu marshallen.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden.  
  
 `pv`  
 Der Schnittstellenzeiger, gemarshallt werden soll; NULL kann sein.  
  
 `dwDestContext`  
 Zielkontext, in dem die angegebene Schnittstelle werden rückgängig gemacht werden.  
  
 Geben Sie eine oder mehrere MSHCTX-Enumerationswerte.  
  
 Methodeninformationen kann derzeit, die entweder in einem anderen Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.  
  
 `pvDestContext`  
 Für die zukünftige Verwendung reserviert. NULL muss sein.  
  
 `mshlflags`  
 Flag, das angibt, ob die Daten, die gemarshallt werden zurück an den Clientprozess übertragen werden – der Normalfall – handschriftlichen auf eine globale Tabelle, in dem von mehreren Clients abgerufen werden können. Geben Sie eine oder mehrere MSHLFLAGS-Enumerationswerte.  
  
 `pSize`  
 Wenn dieser Vorgang abgeschlossen wird, Zeiger auf die obere Grenze für die Menge der Daten in den Marshalling Stream geschrieben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_FAIL oder E_NOINTERFACE.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)
---
title: 'Ftmbase:: MarshalInterface-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc22b83aee62b03ec5e664d08440b00718325272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874615"
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface-Methode
Schreibt in einen Stream der Daten, die erforderlich sind, um eine Proxy-Objekt in einem Clientprozess zu initialisieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pStm`  
 Zeiger auf den Stream während des Marshallens verwendet werden.  
  
 `riid`  
 Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden. Diese Schnittstelle muss von der IUnknown-Schnittstelle abgeleitet werden.  
  
 `pv`  
 Zeiger auf den Schnittstellenzeiger auf das zu marshallende; NULL kann sein, wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle besitzt.  
  
 `dwDestContext`  
 Zielkontext, in dem die angegebene Schnittstelle werden rückgängig gemacht werden.  
  
 Geben Sie eine oder mehrere MSHCTX-Enumerationswerte.  
  
 Methodeninformationen kann in einem anderen Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.  
  
 `pvDestContext`  
 Für die zukünftige Verwendung reserviert. Muss 0 (null) sein.  
  
 `mshlflags`  
 Gibt an, ob die Daten, die gemarshallt werden zurück an den Clientprozess übertragen werden – der Normalfall – handschriftlichen auf eine globale Tabelle, in dem von mehreren Clients abgerufen werden können.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Der Schnittstellenzeiger wurde erfolgreich gemarshallt.  
  
 E_NOINTERFACE  
 Die angegebene Schnittstelle wird nicht unterstützt.  
  
 STG_E_MEDIUMFULL  
 Der Datenstrom ist voll.  
  
 E_FAIL  
 Fehler bei diesem Vorgang.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)
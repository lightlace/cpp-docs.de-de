---
title: 'Ftmbase:: MarshalInterface-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: ff0c1a5e41dfe46f2d88aeeb3093dbc9ee4d4005
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570056"
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
  
### <a name="parameters"></a>Parameter  
 *pStm*  
 Zeiger auf den Stream, der während des Marshalling verwendet werden.  
  
 *riid*  
 Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll. Diese Schnittstelle muss von abgeleitet werden die `IUnknown` Schnittstelle.  
  
 *PV*  
 Zeiger auf den Schnittstellenzeiger auf das zu marshallende; Wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle verfügt, kann NULL sein.  
  
 *dwDestContext*  
 Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.  
  
 Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.  
  
 Rückgängigmachen des Marshallens kann in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.  
  
 *pvDestContext*  
 Für die zukünftige Verwendung reserviert. Muss 0 (null) sein.  
  
 *mshlflags*  
 Gibt an, ob die Daten gemarshallt werden zurück an den Prozess der übertragen werden – der Normalfall – oder in einer globalen Tabelle, in dem sie, indem mehrere Clients abgerufen werden geschrieben.  
  
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
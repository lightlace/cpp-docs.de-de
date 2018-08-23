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
ms.openlocfilehash: a95521123a87a6ae68ce9f923779c1a6ceda4ccf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599710"
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface-Methode

Schreibt in einen Stream der Daten, die erforderlich sind, um eine Proxy-Objekt in einem Clientprozess zu initialisieren.

## <a name="syntax"></a>Syntax

```cpp
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

S_OK zurück, die der Schnittstellenzeiger auf erfolgreich gemarshallt wurde.

E_NOINTERFACE an die angegebene Schnittstelle wird nicht unterstützt.

STG_E_MEDIUMFULL der Datenstrom ist voll.

Fehler bei der E_FAIL den Vorgang.

## <a name="requirements"></a>Anforderungen

**Header:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[FtmBase-Klasse](../windows/ftmbase-class.md)
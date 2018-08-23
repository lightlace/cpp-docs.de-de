---
title: 'Ftmbase:: GetUnmarshalClass-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c76c2d75f3d8c2e872b29d9ecf07841c99027713
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599502"
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass-Methode

Ruft die CLSID, die COM verwendet, um die DLL, die den Code für den entsprechenden Proxy zu suchen. COM lädt diese DLL-Datei um eine nicht initialisierte Instanz des Proxys zu erstellen.

## <a name="syntax"></a>Syntax

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Parameter

*riid*  
Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll.

*PV*  
Zeiger auf die Schnittstelle, die gemarshallt werden; Wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle verfügt, kann NULL sein.

*dwDestContext*  
Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.

Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.

Rückgängigmachen des Marshallens kann entweder in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.

*pvDestContext*  
Für die zukünftige Verwendung reserviert. NULL muss sein.

*mshlflags*  
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf die CLSID zum Erstellen eines Proxys im Clientprozess verwendet werden.

*pCid*

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls S_FALSE.

## <a name="requirements"></a>Anforderungen

**Header:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[FtmBase-Klasse](../windows/ftmbase-class.md)
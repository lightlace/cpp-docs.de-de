---
title: 'Ftmbase:: Createglobalinterfacetable-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c042b6bd17da3459f499f9eb1c9167343c2e2ab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578772"
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable-Methode

Erstellt eine globale Schnittstellentabelle (GIT).

## <a name="syntax"></a>Syntax

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Parameter

*Git*  
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf eine globale Schnittstellentabelle.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter der `IGlobalInterfaceTable` Thema in der **COM-Schnittstellen** Unterthema der **COM-Verweises** in der MSDN Library.

## <a name="requirements"></a>Anforderungen

**Header:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[FtmBase-Klasse](../windows/ftmbase-class.md)
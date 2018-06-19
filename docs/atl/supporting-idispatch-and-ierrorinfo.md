---
title: Unterstützung der IDispatch und IErrorInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94f4c99da3989cce84bd5b6bd3bbfee8df97ff43
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360948"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Unterstützung der IDispatch und IErrorInfo
Können Sie die Vorlagenklasse [IDispatchImpl](../atl/reference/idispatchimpl-class.md) , geben Sie eine Standardimplementierung der `IDispatch Interface` Teil jeder dualen Schnittstellen für das Objekt.  
  
 Wenn Ihr Objekt verwendet die `IErrorInfo` Schnittstelle zum Melden von Fehlern zurück an den Client, dann muss Ihr Objekt unterstützen die `ISupportErrorInfo Interface` Schnittstelle. Die Vorlagenklasse [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) bietet eine einfache Möglichkeit zur Implementierung dieser Funktion, wenn Sie nur eine einzelne Schnittstelle verfügen, die Fehler für das Objekt generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)


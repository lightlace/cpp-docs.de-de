---
title: "Unterstützung der IDispatch und IErrorInfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs: C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6d34f0d0616ae3980d1132b1f70812fe273d275
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Unterstützung der IDispatch und IErrorInfo
Können Sie die Vorlagenklasse [IDispatchImpl](../atl/reference/idispatchimpl-class.md) , geben Sie eine Standardimplementierung der `IDispatch Interface` Teil jeder dualen Schnittstellen für das Objekt.  
  
 Wenn Ihr Objekt verwendet die `IErrorInfo` Schnittstelle zum Melden von Fehlern zurück an den Client, dann muss Ihr Objekt unterstützen die `ISupportErrorInfo Interface` Schnittstelle. Die Vorlagenklasse [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) bietet eine einfache Möglichkeit zur Implementierung dieser Funktion, wenn Sie nur eine einzelne Schnittstelle verfügen, die Fehler für das Objekt generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)


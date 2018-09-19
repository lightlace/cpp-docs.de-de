---
title: Unterstützen von IDispatch und IErrorInfo | Microsoft-Dokumentation
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
ms.openlocfilehash: 0d9c27dfe81c3bbd2978f418c8e942ac20190b30
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753607"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Unterstützen von IDispatch und IErrorInfo

Können Sie die Vorlagenklasse [IDispatchImpl](../atl/reference/idispatchimpl-class.md) zu einer standardmäßigen Implementierung von der `IDispatch Interface` Teil aller duale Schnittstellen für das Objekt.

Wenn das Objekt verwendet die `IErrorInfo` Schnittstelle zum Melden von Fehlern zurück an den Client, und dann das Objekt muss unterstützen die `ISupportErrorInfo Interface` Schnittstelle. Die Vorlagenklasse [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) bietet eine einfache Möglichkeit, dies zu implementieren, wenn Sie nur eine einzige Benutzeroberfläche verfügen, die Fehler für das Objekt generiert.

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)


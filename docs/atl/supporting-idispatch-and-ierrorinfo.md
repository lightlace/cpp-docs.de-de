---
title: Unterstützen von IDispatch und IErrorInfo
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 2dcebd215ff5e1bdf72323323dfbaebd16fa3403
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342024"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Unterstützen von IDispatch und IErrorInfo

Können Sie die Vorlagenklasse [IDispatchImpl](../atl/reference/idispatchimpl-class.md) zu einer standardmäßigen Implementierung von der `IDispatch Interface` Teil aller duale Schnittstellen für das Objekt.

Wenn das Objekt verwendet die `IErrorInfo` Schnittstelle zum Melden von Fehlern zurück an den Client, und dann das Objekt muss unterstützen die `ISupportErrorInfo Interface` Schnittstelle. Die Vorlagenklasse [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) bietet eine einfache Möglichkeit, dies zu implementieren, wenn Sie nur eine einzige Benutzeroberfläche verfügen, die Fehler für das Objekt generiert.

## <a name="see-also"></a>Siehe auch

[Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md)

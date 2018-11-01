---
title: Schnittstellen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 3f6e8978c01d6689118a3a004c48e75a40151490
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594739"
---
# <a name="interfaces-atl"></a>Schnittstellen (ATL)

Eine Schnittstelle ist die Möglichkeit, in der ein Objekt seine Funktionalität für die Außenwelt verfügbar macht. Bei COM ist eine Schnittstelle für eine Tabelle von Zeigern (z. B. eine C++-Vtable) auf Funktionen, die vom Objekt implementiert. In der Tabelle stellt die Schnittstelle dar, und die Funktionen, die auf denen er zeigt, sind die Methoden dieser Schnittstelle. Ein Objekt kann beliebig viele Schnittstellen verfügbar machen.

Jede Schnittstelle basiert darauf, dass die grundlegende Schnittstelle für COM- [IUnknown](../atl/iunknown.md). Die Methoden der `IUnknown` verhindert die Navigation zu anderen Schnittstellen, die vom Objekt verfügbar gemacht.

Darüber hinaus wird jeder Schnittstelle eine eindeutige ID (IID)-Schnittstelle angegeben. Diese Eindeutigkeit erleichtert die Unterstützung. Eine neue Version einer Schnittstelle ist einfach eine neue Schnittstelle mit einer neuen IID.

> [!NOTE]
>  Die IIDs für die standard-COM und OLE-Schnittstellen sind vordefiniert.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[COM-Objekte und Schnittstellen](/windows/desktop/com/com-objects-and-interfaces)


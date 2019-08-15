---
title: Schnittstellen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 2373351330982623ffa602fd81bec61d0bc257b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492139"
---
# <a name="interfaces-atl"></a>Schnittstellen (ATL)

Eine Schnittstelle ist die Methode, mit der ein Objekt seine Funktionalität der Außenwelt verfügbar macht. In com ist eine Schnittstelle eine Tabelle mit Zeigern (z C++ . b. eine Vtable) für Funktionen, die vom-Objekt implementiert werden. Die Tabelle stellt die-Schnittstelle dar, und die Funktionen, auf die Sie verweist, sind die Methoden dieser Schnittstelle. Ein-Objekt kann beliebig viele Schnittstellen verfügbar machen.

Jede Schnittstelle basiert auf der grundlegenden com-Schnittstelle [IUnknown](../atl/iunknown.md). Die Methoden von `IUnknown` ermöglichen die Navigation zu anderen Schnittstellen, die vom-Objekt verfügbar gemacht werden.

Außerdem erhält jede Schnittstelle eine eindeutige Schnittstellen-ID (IID). Diese Eindeutigkeit erleichtert die Unterstützung der Schnittstellen Versionsverwaltung. Eine neue Version einer Schnittstelle ist einfach eine neue Schnittstelle mit einer neuen IID.

> [!NOTE]
>  IIDs für die Standard-com-und OLE-Schnittstellen sind vordefiniert.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[COM-Objekte und-Schnittstellen](/windows/win32/com/com-objects-and-interfaces)

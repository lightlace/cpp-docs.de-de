---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IUnknown
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 760db28f4016ed529b45c72d25eaabf664642cd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430042"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) ist die Basisschnittstelle jeder zweiten COM-Schnittstelle.  Diese Schnittstelle definiert drei Methoden: [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), und [Version](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) ermöglicht einem Schnittstellenbenutzer, um das Objekt ein Zeiger auf einer seiner anderen Schnittstellen anzufordern. ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) und [Version](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) implementieren die verweiszählung für die Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[IUnknown und Schnittstellenvererbung](/windows/desktop/com/iunknown-and-interface-inheritance)


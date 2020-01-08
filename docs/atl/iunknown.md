---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 6adfbdc59b2a63aa2f2bb39e27139ca977ba9465
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298752"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) ist die Basisschnittstelle jeder anderen COM-Schnittstelle.  Diese Schnittstelle definiert drei Methoden: [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)), [adressf](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)und [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) ermöglicht es einem Schnittstellen Benutzer, das Objekt nach einem Zeiger auf eine andere Schnittstelle zu Fragen. [Adressf](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref) und [Release](/windows/win32/api/unknwn/nf-unknwn-iunknown-release) implementieren Verweis Zähler für die Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Einführung in COM](../atl/introduction-to-com.md)<br/>
[IUnknown und Schnittstellen Vererbung](/windows/win32/com/iunknown-and-interface-inheritance)

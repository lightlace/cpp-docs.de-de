---
title: IUnknown | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acabc38b115429c88ac9bed0e509cbcadd78a5aa
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217495"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) ist die Basisschnittstelle jeder zweiten COM-Schnittstelle.  Diese Schnittstelle definiert drei Methoden: [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), und [Version](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) ermöglicht einem Schnittstellenbenutzer, um das Objekt ein Zeiger auf einer seiner anderen Schnittstellen anzufordern. ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) und [Version](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) implementieren die verweiszählung für die Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [IUnknown und Schnittstellenvererbung](/windows/desktop/com/iunknown-and-interface-inheritance)


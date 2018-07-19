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
ms.openlocfilehash: d832d2978bf9db82b290d77b236fea1c9bcada58
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953041"
---
# <a name="iunknown"></a>IUnknown
[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ist die Basisschnittstelle jeder zweiten COM-Schnittstelle.  Diese Schnittstelle definiert drei Methoden: [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), ["AddRef"](http://msdn.microsoft.com/library/windows/desktop/ms691379), und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317). [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) ermöglicht einem Schnittstellenbenutzer, um das Objekt ein Zeiger auf einer seiner anderen Schnittstellen anzufordern. ["AddRef"](http://msdn.microsoft.com/library/windows/desktop/ms691379) und [Version](http://msdn.microsoft.com/library/windows/desktop/ms682317) implementieren die verweiszählung für die Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [IUnknown und Schnittstellenvererbung](http://msdn.microsoft.com/library/windows/desktop/ms692713)


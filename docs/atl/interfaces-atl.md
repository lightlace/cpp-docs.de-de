---
title: Schnittstellen (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359313"
---
# <a name="interfaces-atl"></a>Schnittstellen (ATL)
Eine Schnittstelle ist die Möglichkeit, in der ein Objekt seine Funktionalität an die Außenwelt verfügbar macht. In COM ist eine Schnittstelle eine Tabelle von Zeigern (z. B. eine C++-Vtable) auf Funktionen, die von dem Objekt implementiert. Die Tabelle stellt die Schnittstelle dar, und die Funktionen, die auf denen er zeigt, sind die Methoden dieser Schnittstelle. Ein Objekt kann beliebig viele Schnittstellen verfügbar machen.  
  
 Jede Schnittstelle basiert auf der grundlegenden COM-Schnittstelle [IUnknown](../atl/iunknown.md). Die Methoden der **IUnknown** ermöglichen die Navigation zu anderen Schnittstellen, die vom Objekt verfügbar gemacht.  
  
 Darüber hinaus erhält jede Schnittstelle eine eindeutige ID (IID)-Schnittstelle. Diese Eindeutigkeit vereinfacht die Unterstützung. Eine neue Version einer Schnittstelle ist einfach eine neue Schnittstelle mit einer neuen IID.  
  
> [!NOTE]
>  IIDs für die standardmäßigen COM und OLE-Schnittstellen sind vordefiniert.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [COM-Objekte und Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms690343)


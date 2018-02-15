---
title: Schnittstellen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95dce7d707cfb29c8f33f94504c26b5b24ef4c4f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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


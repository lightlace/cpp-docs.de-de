---
title: Schnittstellen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf1dd68a3ca8e6735b07c5bd7247b457bd7d246d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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


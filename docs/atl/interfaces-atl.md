---
title: Schnittstellen (ATL) | Microsoft-Dokumentation
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
ms.openlocfilehash: b7becd9e27294c81ce6144d08c79cfac52636fbf
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848264"
---
# <a name="interfaces-atl"></a>Schnittstellen (ATL)
Eine Schnittstelle ist die Möglichkeit, in der ein Objekt seine Funktionalität für die Außenwelt verfügbar macht. Bei COM ist eine Schnittstelle für eine Tabelle von Zeigern (z. B. eine C++-Vtable) auf Funktionen, die vom Objekt implementiert. In der Tabelle stellt die Schnittstelle dar, und die Funktionen, die auf denen er zeigt, sind die Methoden dieser Schnittstelle. Ein Objekt kann beliebig viele Schnittstellen verfügbar machen.  
  
 Jede Schnittstelle basiert darauf, dass die grundlegende Schnittstelle für COM- [IUnknown](../atl/iunknown.md). Die Methoden der `IUnknown` verhindert die Navigation zu anderen Schnittstellen, die vom Objekt verfügbar gemacht.  
  
 Darüber hinaus wird jeder Schnittstelle eine eindeutige ID (IID)-Schnittstelle angegeben. Diese Eindeutigkeit erleichtert die Unterstützung. Eine neue Version einer Schnittstelle ist einfach eine neue Schnittstelle mit einer neuen IID.  
  
> [!NOTE]
>  Die IIDs für die standard-COM und OLE-Schnittstellen sind vordefiniert.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in COM](../atl/introduction-to-com.md)   
 [COM-Objekte und Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms690343)


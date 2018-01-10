---
title: nonextensible-Attribut | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: nonextensible
dev_langs: C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af16748bb3b2048ce854ccc7a03b2400039184a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nonextensible-attribute"></a>nonextensible-Attribut
Wenn eine duale Schnittstelle zur Laufzeit nicht erweitert wird (d. h. Sie wird nicht bereitstellen, Methoden oder Eigenschaften über **IDispatch:: Invoke** , die nicht über die Vtable verfügbar sind), sollten Sie übernehmen die **nonextensible** -Attribut auf die Schnittstellendefinition. Dieses Attribut stellt die Informationen zu Clientsprachen (z. B. Visual Basic), die zum Aktivieren der codeüberprüfung der vollständige zum Zeitpunkt der Kompilierung verwendet werden kann. Wenn dieses Attribut nicht angegeben wird, können Fehler im Clientcode bleiben bis zur Laufzeit ausgeblendet.  
  
 Weitere Informationen zu den **nonextensible** Attribut und ein Beispiel finden Sie unter [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

